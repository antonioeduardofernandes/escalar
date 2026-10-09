# Arquitetura técnica do Escalar

**Status:** planejamento técnico em andamento
**Produto:** Escalar — Sistema de Gestão de Escalas Hospitalares

## 1. Objetivo

Este documento estabelece as decisões e diretrizes técnicas para a construção do Escalar. O objetivo é criar uma base coerente, segura, sustentável e adequada ao MVP, reduzindo decisões improvisadas durante a implementação.

O Escalar deve priorizar simplicidade, segurança, rastreabilidade, integridade dos dados e desempenho. A arquitetura deverá atender às necessidades atuais sem impedir uma futura migração para infraestrutura mais robusta.

Este documento complementa as regras de negócio e a especificação de interface registradas nos demais documentos do projeto. Em caso de divergência, as regras de negócio aprovadas prevalecem sobre decisões de implementação ou conveniência técnica.

## 2. Princípios arquiteturais

1. **Regras de negócio centralizadas:** as regras operacionais devem estar documentadas e ser implementadas de maneira consistente.
2. **Backend como autoridade:** validações críticas e permissões não podem depender exclusivamente do navegador.
3. **Segurança por padrão:** dados e operações devem estar protegidos por autenticação, autorização e controle de acesso.
4. **Histórico preservado:** alterações relevantes, materializações, fechamentos e reaberturas devem respeitar as regras de auditoria e versionamento.
5. **Separação de responsabilidades:** interface, regras de negócio, persistência e autenticação devem ter responsabilidades claras.
6. **Simplicidade operacional:** não introduzir serviços, camadas ou dependências sem necessidade concreta.
7. **Desempenho:** priorizar respostas rápidas, especialmente na edição e validação da matriz mensal de escalas.
8. **Evolução planejada:** evitar dependências desnecessárias que dificultem a migração de infraestrutura ou a evolução da aplicação.
9. **Integridade transacional:** operações que alterem conjuntamente dados, versões, estados e auditoria devem evitar resultados parciais ou inconsistentes.
10. **Decisões explícitas:** o agente de desenvolvimento não deve inventar regras de negócio para preencher lacunas documentais. Dúvidas relevantes devem ser registradas para decisão.

## 3. Tecnologias definidas

### 3.1. Aplicação

A base tecnológica aprovada é:

* **SvelteKit:** framework principal da aplicação.
* **Svelte 5:** tecnologia para construção da interface.
* **TypeScript:** linguagem principal, com tipagem aplicada ao código.
* **Vite:** ferramenta de desenvolvimento e compilação integrada ao SvelteKit.
* **Tailwind CSS:** estilização, espaçamento, cores e responsividade.
* **shadcn-svelte:** base de componentes reutilizáveis e personalizáveis.
* **Lucide Icons:** biblioteca de ícones.

A matriz de escalas é um componente central do produto e poderá exigir implementação específica, otimizada para edição, rolagem, filtros e atualização dos indicadores.

A escolha dessas tecnologias não autoriza a inclusão indiscriminada de bibliotecas adicionais. Novas dependências devem ter finalidade clara e ser compatíveis com a stack aprovada.

### 3.2. Backend e banco de dados

A infraestrutura inicialmente prevista utiliza:

* **Supabase:** serviço para PostgreSQL, autenticação e recursos controlados de acesso aos dados.
* **PostgreSQL:** banco de dados relacional.
* **Row Level Security (RLS):** proteção de acesso aos registros no banco de dados.

A utilização do Supabase não elimina a necessidade de modelar corretamente as permissões, as regras de negócio, as transações e os limites de confiança entre navegador e servidor.

As operações críticas deverão ser executadas por mecanismos confiáveis no backend, com validação de permissões e estado atual dos registros antes da confirmação.

### 3.3. Hospedagem e versionamento

A infraestrutura inicial proposta é:

* **GitHub:** repositório e histórico do código-fonte.
* **Netlify:** hospedagem da aplicação de demonstração do MVP.
* **Supabase:** infraestrutura inicial de banco de dados e autenticação.

A estratégia de utilizar planos gratuitos é uma forma de reduzir o custo inicial, não uma garantia de gratuidade, disponibilidade ou capacidade permanente.

Antes da implantação, deverão ser verificadas as limitações vigentes de uso, armazenamento, tráfego, autenticação, backups, implantação e demais recursos de cada serviço.

## 4. Ambientes e implantação

### 4.1. Desenvolvimento

O desenvolvimento e os testes ocorrerão prioritariamente em ambiente local, utilizando dados fictícios.

O código deverá ser versionado no GitHub. O fluxo proposto utiliza:

* `develop`: integração e validação das alterações em desenvolvimento.
* `main`: versão considerada estável para demonstração ou implantação controlada.

A estratégia de branches deverá ser formalizada antes da implementação. Alterações não deverão ser publicadas automaticamente em todos os ambientes apenas por terem sido commitadas.

### 4.2. Implantação controlada

A publicação no Netlify deverá ocorrer de maneira controlada, após revisão e validação das alterações.

O fluxo deverá evitar consumo desnecessário de créditos e recursos durante o desenvolvimento.

Antes de cada publicação, deverão ser verificadas:

1. As alterações incluídas na versão.
2. A execução dos testes aplicáveis.
3. As configurações e variáveis de ambiente.
4. A compatibilidade da compilação com o ambiente de hospedagem.
5. A versão que será publicada.
6. O funcionamento da aplicação após a implantação.

A integração exata entre GitHub e Netlify permanece pendente de configuração e validação técnica.

### 4.3. Estratégia de renderização e build

A aplicação deverá utilizar a estratégia de renderização mais simples que atenda aos requisitos de autenticação, autorização, desempenho e implantação.

A geração estática poderá ser utilizada para as partes compatíveis com esse modelo. Não se deverá introduzir SSR ou funções de servidor sem necessidade concreta.

Entretanto, a escolha de geração estática não poderá comprometer a proteção dos dados, as operações privilegiadas ou a validação no backend.

Antes da implementação, será necessário definir e testar:

* A configuração de build do SvelteKit para Netlify.
* A estratégia de carregamento de dados das telas autenticadas.
* O tratamento de rotas protegidas e de sessões.
* O local de execução das operações críticas.
* A compatibilidade entre autenticação, RLS e os mecanismos de backend utilizados.

A compilação e a publicação deverão ser testadas com a configuração real escolhida. Não se deve presumir que uma configuração exclusivamente estática atenderá a todas as necessidades antes dessa validação.

### 4.4. Limitações do MVP

O MVP deverá utilizar exclusivamente dados fictícios.

Não deverão ser inseridos dados reais de servidores, informações institucionais restritas ou informações pessoais reais antes da aprovação institucional e da definição dos requisitos necessários de segurança, privacidade, proteção de dados e operação.

A demonstração deverá ser tratada como ambiente de avaliação, não como ambiente autorizado para operação institucional real.

A arquitetura deverá permitir evolução posterior para infraestrutura paga, sem exigir reconstrução desnecessária da aplicação.

## 5. Organização lógica da aplicação

A aplicação deverá separar as seguintes responsabilidades.

### 5.1. Interface

Responsável por apresentar informações, receber interações, indicar estados e fornecer feedback ao usuário.

A interface poderá realizar validações preliminares para melhorar a experiência, mas não será a única responsável por impor regras críticas.

### 5.2. Regras de negócio

Responsáveis por interpretar e aplicar as regras documentadas do Escalar, incluindo:

* Validação de turnos e períodos de descanso.
* Identificação de sobreposições e conflitos.
* Aplicação de modelos de escala.
* Cálculo de horas planejadas.
* Ocorrências e compensações.
* Dimensionamento.
* Materialização, fechamento e reabertura.
* Controle de publicação de versões.
* Verificação de permissões operacionais.

Regras críticas deverão ser verificadas em uma camada confiável do backend antes da confirmação das operações correspondentes.

A implementação deverá evitar que a mesma regra seja reproduzida de maneiras divergentes em diferentes telas ou serviços.

### 5.3. Persistência

Responsável por armazenar dados operacionais, relacionamentos, estados, versões e registros de auditoria.

As operações deverão preservar a integridade referencial e impedir atualizações parciais que deixem uma escala em estado inconsistente.

Migrações do banco de dados deverão ser versionadas e executáveis de maneira controlada, com procedimento documentado de aplicação e validação.

### 5.4. Autenticação e autorização

A autenticação identifica o usuário. A autorização determina quais operações e informações ele pode acessar.

As permissões deverão considerar conjuntamente:

* Papel do usuário.
* Escopo organizacional autorizado.
* Estado do registro ou da escala.
* Regra específica da operação.

Ocultar um botão ou item de menu não constitui controle de segurança suficiente.

## 6. Segurança e controle de acesso

### 6.1. Princípios obrigatórios

A arquitetura deverá contemplar:

* Autenticação individual.
* Autorização no backend.
* Políticas RLS para proteger o acesso às tabelas expostas por meio do Supabase.
* Validação de entradas recebidas pela aplicação.
* Proteção de credenciais e segredos fora do código público do navegador.
* Controle das operações sensíveis.
* Tratamento seguro de sessões e recuperação de acesso.
* Registro das operações relevantes para auditoria.
* Restrição do acesso individual do servidor às próprias informações de escala.

Nenhuma tabela com dados protegidos poderá ficar acessível de maneira irrestrita por meio de APIs públicas.

As políticas deverão ser definidas por tabela e operação, incluindo leitura, inserção, atualização e exclusão quando essas operações existirem. O padrão será negar o acesso que não tenha sido explicitamente autorizado.

### 6.2. Papel, escopo e estado

A autorização deverá verificar o papel e o escopo do usuário, além das condições operacionais aplicáveis.

O escopo selecionado na interface não poderá ampliar as permissões concedidas ao usuário. A mudança de unidade deverá apenas alterar o contexto de visualização dentro do escopo já autorizado.

As operações críticas deverão confirmar novamente a autorização e o estado do registro no backend. Não se deve confiar apenas em informações recebidas do navegador.

### 6.3. Operações privilegiadas

Operações que exigem privilégios elevados deverão ser executadas exclusivamente por mecanismos confiáveis no backend.

Credenciais administrativas e chaves privilegiadas do Supabase não poderão ser incluídas no código entregue ao navegador.

O Administrador não receberá automaticamente permissão para materializar, fechar ou reabrir escalas. Essas operações seguirão os papéis e limites já definidos nas regras de negócio.

### 6.4. Testes de segurança

Antes de utilizar dados reais, deverão ser testados, no mínimo:

* Tentativas de acessar dados de outra unidade fora do escopo.
* Tentativas de consultar a escala de outro servidor.
* Tentativas de executar ações incompatíveis com o papel.
* Tentativas de editar escalas materializadas ou fechadas sem autorização.
* Tentativas de contornar permissões alterando requisições no navegador.
* Acesso não autorizado a tabelas e operações por APIs.
* Proteção de segredos e credenciais.
* Expiração, ativação e recuperação de sessões.

A configuração de segurança deverá ser verificada por testes, e não apenas pela existência de políticas declaradas na documentação.

## 7. Integridade e versionamento das escalas

A arquitetura deverá distinguir claramente elaboração, salvamento, validação, materialização, fechamento e reabertura.

Essas operações não são equivalentes.

### 7.1. Salvamento

O salvamento registra alterações no estado de elaboração da escala. Ele não representa, por si só, validação completa, materialização, fechamento ou publicação oficial.

### 7.2. Validação

A validação completa verifica a escala segundo as regras aplicáveis ao seu contexto e período.

A interface poderá realizar verificações incrementais durante a edição, mas a validação autoritativa deverá ocorrer no backend antes da materialização.

Alertas e bloqueios deverão ser tratados de acordo com as regras de negócio, não apenas com a classificação visual.

### 7.3. Materialização

A materialização deverá preservar uma versão identificável da escala planejada, incluindo as informações necessárias para reconstruir o estado oficial daquela versão.

A versão deverá permitir identificar, conforme o modelo de dados definido, o período, a unidade, os servidores e turnos incluídos, o responsável pela operação, a data e os resultados de validação pertinentes.

A materialização não representa confirmação automática do trabalho efetivamente realizado.

### 7.4. Fechamento

O fechamento protege a versão oficial da escala contra alterações ordinárias.

A operação deverá exigir autorização adequada, confirmação explícita e verificação das condições atuais no backend.

A publicação da escala e as notificações decorrentes deverão ser tratadas como etapas identificáveis, sem tornar o fechamento dependente do sucesso imediato do serviço de e-mail.

### 7.5. Reabertura

A reabertura de uma escala fechada será permitida somente ao Supervisor autorizado para aquele escopo, com justificativa obrigatória.

A operação deverá preservar a versão fechada anterior e registrar a ação na auditoria.

Após a reabertura, a escala deverá passar pelo fluxo necessário de revisão, validação, nova materialização, fechamento e publicação.

A nova versão não poderá apagar ou substituir silenciosamente o histórico oficial anterior.

### 7.6. Integridade transacional

Operações que alterem o estado da escala, criem versões oficiais e registrem auditoria deverão ser executadas de maneira consistente.

Quando várias mudanças precisarem ocorrer em conjunto, deverá ser utilizada uma transação ou mecanismo equivalente que evite a confirmação parcial.

As operações críticas também deverão verificar se a escala continua na versão e no estado esperados no momento da confirmação, evitando alterações concorrentes ou obsoletas.

## 8. Concorrência de edição

No MVP, cada escala poderá ter apenas um editor ativo por vez.

Outros usuários autorizados poderão consultar a escala, mas não poderão editá-la enquanto houver um bloqueio de edição válido.

O bloqueio deverá:

* Ser gerenciado pelo backend.
* Ter duração limitada.
* Permitir renovação enquanto a edição estiver ativa.
* Registrar a identificação do editor.
* Expirar ou ser recuperado após falhas de rede ou encerramento inesperado.
* Evitar bloqueios permanentes.
* Impedir que dois usuários gravem simultaneamente como se fossem o único editor.

A interface deverá indicar quem está editando e comunicar quando a edição estiver indisponível.

A arquitetura deverá evitar dependências que impeçam uma futura evolução para edição simultânea, sem implementar essa complexidade no MVP.

## 9. Desempenho da matriz

A edição da matriz mensal deverá priorizar atualizações locais e validações incrementais quando possível.

A aplicação não deverá recalcular indiscriminadamente toda a escala a cada interação se for possível verificar apenas os elementos afetados.

Isso não dispensa a validação completa e autoritativa no backend antes da materialização.

A interface deverá tratar estados de salvamento, falha de conexão e alterações pendentes. Não poderá indicar que uma alteração foi salva antes da confirmação do backend.

A estratégia de implementação deverá ser testada com volumes representativos de servidores e dias do mês, utilizando dados fictícios.

## 10. E-mail e notificações

O Escalar deverá utilizar notificações por e-mail para:

* Ativação de conta.
* Recuperação de acesso.
* Comunicação de fechamento e publicação de escala.
* Comunicação de uma nova versão após reabertura, revisão e novo fechamento.

O provedor de e-mail permanece pendente de seleção. A escolha deverá considerar custo, limites de envio, segurança, confiabilidade e compatibilidade com a hospedagem.

### 10.1. Fluxo de publicação

Após o fechamento válido de uma escala, o sistema deverá registrar a versão oficial e iniciar o processo de notificação aos servidores afetados.

O envio de e-mail deverá ser desacoplado da operação principal de fechamento. Uma falha de envio não deverá desfazer um fechamento confirmado.

A arquitetura deverá permitir identificar notificações pendentes ou com falha e estabelecer um mecanismo de nova tentativa ou tratamento operacional.

A notificação deverá conter um link seguro para consulta, sem anexar automaticamente um PDF a todos os destinatários.

### 10.2. Acesso individual

O link não poderá permitir acesso público ou irrestrito às escalas individuais.

O servidor deverá autenticar-se e visualizar somente sua própria escala atual. Após a autenticação, deverá ser encaminhado diretamente à área de consulta individual, quando aplicável.

O sistema não deverá depender de ocultação de elementos da interface para impedir acesso a dados de outros servidores.

### 10.3. Ativação e recuperação de conta

A ativação inicial deverá ocorrer por meio de link seguro, com validade limitada e uso único, enviado ao e-mail cadastrado.

O servidor definirá sua própria senha. Senhas não deverão ser enviadas por e-mail ou compartilhadas manualmente pelo Administrador.

A recuperação de acesso deverá usar link temporário e de uso único. A resposta da interface não deverá revelar indevidamente se determinado e-mail possui conta cadastrada.

## 11. Auditoria e retenção

A arquitetura deverá preservar o histórico das operações relevantes e das versões oficiais das escalas.

O modelo de auditoria deverá permitir identificar, conforme o evento:

* Usuário responsável.
* Data e horário.
* Tipo de operação.
* Registro ou escala afetada.
* Estado ou versão relacionado à operação.
* Justificativa, quando obrigatória.
* Resultado da operação.

O esquema definitivo dos eventos, a política de retenção e os mecanismos de consulta ainda deverão ser detalhados antes da implementação correspondente.

O histórico oficial não poderá ser apagado ou alterado por operações ordinárias de interface. As permissões administrativas também não deverão contornar as regras de versionamento e auditoria.

## 12. Testes e qualidade

Antes da implantação, deverão ser estabelecidas verificações automatizadas e procedimentos de validação para:

* Regras de negócio críticas.
* Permissões por papel e escopo.
* Políticas RLS.
* Integridade dos dados e migrações.
* Edição e salvamento da matriz.
* Concorrência e expiração de bloqueios de edição.
* Materialização, fechamento e reabertura.
* Preservação de versões históricas.
* Acesso individual às escalas.
* Notificações e tratamento de falhas.
* Comportamento diante de falhas de rede e persistência.
* Fluxos essenciais da interface.
* Compilação e implantação no ambiente escolhido.

O agente de desenvolvimento deverá implementar e executar os testes previstos e apresentar os resultados.

Decisões de negócio não documentadas deverão ser encaminhadas para definição, e não inventadas durante a implementação.

## 13. Decisões técnicas pendentes

Os seguintes pontos deverão ser definidos ou validados antes da implementação correspondente:

1. Estrutura detalhada do projeto SvelteKit e organização dos módulos.
2. Estratégia final de renderização e configuração do build para Netlify.
3. Modelo relacional do banco, migrações e versionamento do esquema.
4. Distribuição das regras entre aplicação, servidor e banco de dados.
5. Matriz de políticas RLS por tabela e operação.
6. Fluxos privilegiados do backend e proteção de credenciais.
7. Provedor e fluxo de envio de e-mails.
8. Política de backups, recuperação e retenção.
9. Esquema de auditoria e consulta do histórico.
10. Expiração de sessão e parâmetros de segurança.
11. Procedimento definitivo de integração e implantação.
12. Estratégia de testes automatizados e critérios mínimos de aprovação.
13. Verificação das limitações e dos custos vigentes dos serviços escolhidos.

Essas pendências não autorizam a alteração unilateral das regras de negócio já aprovadas. A definição de uma pendência deverá ocorrer antes da implementação que dependa dela.

## 14. Diretriz final

A arquitetura do Escalar deverá ser a mais simples possível entre as alternativas que atendam aos requisitos de segurança, integridade, desempenho, auditoria e evolução do produto.

A adoção de novas tecnologias, serviços ou camadas deverá ser justificada por uma necessidade concreta.

**O planejamento técnico define como as regras aprovadas serão implementadas; não concede ao agente autonomia para redefinir essas regras.**
