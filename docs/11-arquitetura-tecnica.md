# Arquitetura técnica do Escalar

**Status:** planejamento técnico em andamento
**Produto:** Escalar — Sistema de Gestão de Escalas Hospitalares

## 1. Objetivo

Este documento registra as decisões e diretrizes técnicas para a construção do Escalar. Seu objetivo é estabelecer uma base coerente, segura, sustentável e adequada ao MVP, reduzindo decisões improvisadas durante a implementação.

O Escalar deve priorizar a simplicidade, a segurança, a rastreabilidade e o desempenho. A arquitetura deve atender às necessidades atuais sem impedir uma futura migração para infraestrutura mais robusta.

Este documento complementa, mas não substitui, as regras de negócio registradas nos demais documentos do projeto.

## 2. Princípios arquiteturais

1. **Regras de negócio centralizadas:** as regras operacionais devem ser definidas na documentação e implementadas de maneira consistente, evitando duplicações contraditórias.
2. **Backend como autoridade:** validações críticas e permissões não podem depender exclusivamente do navegador.
3. **Segurança por padrão:** dados e operações devem estar protegidos por autenticação, autorização e controle de acesso.
4. **Histórico preservado:** alterações relevantes, materializações, fechamentos e reaberturas devem respeitar as regras de auditoria e versionamento.
5. **Separação de responsabilidades:** interface, regras de negócio, persistência e autenticação devem ter responsabilidades claras.
6. **Simplicidade operacional:** não introduzir serviços ou camadas sem necessidade concreta.
7. **Desempenho:** priorizar respostas rápidas, especialmente na edição e validação da matriz mensal de escalas.
8. **Evolução planejada:** evitar dependências desnecessárias que dificultem a migração de infraestrutura ou a evolução da aplicação.

## 3. Tecnologias definidas

### 3.1. Aplicação

* **SvelteKit:** framework principal da aplicação.
* **Svelte 5:** tecnologia para construção da interface.
* **TypeScript:** linguagem principal, com tipagem aplicada ao código.
* **Vite:** ferramenta de desenvolvimento e compilação utilizada pelo SvelteKit.
* **Tailwind CSS:** estilização, espaçamento, cores e responsividade.
* **shadcn-svelte:** base de componentes reutilizáveis e personalizáveis.
* **Lucide Icons:** biblioteca de ícones da interface.

A matriz de escalas é um componente central do produto e poderá exigir implementação específica, otimizada para edição, rolagem, filtros e atualização dos indicadores.

### 3.2. Backend e banco de dados

* **Supabase:** serviço inicialmente previsto para PostgreSQL, autenticação e recursos de acesso aos dados.
* **PostgreSQL:** banco de dados relacional.
* **Row Level Security (RLS):** mecanismo de proteção de acesso aos registros, quando aplicável à arquitetura definida.

O uso do Supabase não elimina a necessidade de modelar corretamente as permissões, as regras de negócio e as transações. A arquitetura deverá definir quais operações podem ser executadas diretamente por clientes autorizados e quais exigem uma camada de servidor confiável.

### 3.3. Hospedagem e versionamento

* **GitHub:** repositório e histórico do código-fonte.
* **Netlify:** hospedagem inicialmente prevista para a demonstração do MVP.
* **Supabase:** infraestrutura inicial de banco de dados e autenticação.

A escolha de serviços gratuitos é uma estratégia para reduzir o custo inicial, não uma garantia de disponibilidade ou gratuidade permanente.

Antes da implantação, deverão ser verificadas as limitações vigentes de uso, armazenamento, tráfego, autenticação, backups, implantação e demais recursos de cada plano.

## 4. Ambientes e estratégia de implantação

### 4.1. Desenvolvimento

O desenvolvimento e os testes devem ocorrer prioritariamente em ambiente local, com dados fictícios.

As alterações devem ser versionadas no GitHub. O fluxo de trabalho proposto utiliza:

* `develop`: integração e validação das alterações em desenvolvimento.
* `main`: versão considerada estável para demonstração ou implantação controlada.

A estratégia de branches deverá ser formalizada antes da implementação.

### 4.2. Implantação

A implantação no Netlify deverá ocorrer de maneira controlada, após revisão e validação das alterações.

Não se pretende publicar automaticamente cada alteração ou cada branch durante o desenvolvimento. A configuração final de deploy deverá evitar consumo desnecessário de créditos e recursos.

O procedimento de implantação deverá incluir, no mínimo:

1. Verificação das alterações.
2. Execução dos testes aplicáveis.
3. Verificação das configurações e variáveis de ambiente.
4. Confirmação da versão que será publicada.
5. Implantação controlada.
6. Verificação de funcionamento após a publicação.

O fluxo exato entre GitHub e Netlify permanece pendente de configuração e validação técnica.

### 4.3. Limitações do MVP

O MVP deverá utilizar exclusivamente dados fictícios.

Não devem ser inseridos dados reais de servidores, informações institucionais restritas ou informações pessoais reais antes da aprovação institucional e da definição dos requisitos adequados de segurança, privacidade, proteção de dados e operação.

A demonstração deverá deixar claro que se trata de uma versão de avaliação, não de um ambiente autorizado para operação institucional real.

## 5. Arquitetura da aplicação

A aplicação deverá separar logicamente as seguintes responsabilidades:

### 5.1. Interface

Responsável por apresentar informações, receber interações, indicar estados e fornecer feedback ao usuário.

A interface pode realizar validações preliminares para melhorar a experiência, mas não deve ser a única responsável por impor regras críticas.

### 5.2. Regras de negócio

Responsáveis por interpretar e aplicar as regras documentadas do Escalar, incluindo:

* Validação de turnos e períodos de descanso.
* Identificação de sobreposições e conflitos.
* Aplicação de modelos de escala.
* Cálculo de horas planejadas.
* Ocorrências e compensações.
* Dimensionamento.
* Materialização, fechamento e reabertura.
* Verificação de permissões operacionais.

Regras críticas devem ser verificadas em uma camada confiável do backend antes da confirmação das operações correspondentes.

### 5.3. Persistência

Responsável por armazenar os dados operacionais, os relacionamentos, os estados, as versões e os registros de auditoria necessários.

As alterações devem preservar a integridade referencial e impedir atualizações parciais que deixem a escala em estado inconsistente.

### 5.4. Autenticação e autorização

A autenticação identifica o usuário. A autorização determina quais operações e informações ele pode acessar.

As permissões devem considerar simultaneamente:

* Papel do usuário.
* Escopo organizacional autorizado.
* Estado do registro ou da escala.
* Regra específica da operação.

Ocultar um botão ou item de menu não constitui controle de segurança suficiente.

## 6. Segurança e controle de acesso

A arquitetura deverá contemplar:

* Autenticação individual.
* Controle de acesso no backend.
* Políticas de acesso aos dados compatíveis com os papéis e escopos.
* Proteção de credenciais e segredos fora do código público do navegador.
* Validação de entradas recebidas pela aplicação.
* Proteção das operações sensíveis contra execução não autorizada.
* Tratamento seguro de sessões e recuperação de acesso.
* Registro das operações relevantes para auditoria.
* Acesso individual do servidor restrito às próprias informações de escala.

O Administrador não deverá receber automaticamente permissão para materializar, fechar ou reabrir escalas. Essas operações seguem as regras de papéis já aprovadas no projeto.

Os detalhes de autenticação, recuperação de senha, expiração de sessão, ativação de conta e configuração das políticas RLS deverão ser formalizados em uma especificação de segurança antes da implementação.

## 7. Integridade e versionamento das escalas

A arquitetura deverá distinguir os estados de elaboração, materialização e fechamento conforme as regras de negócio.

A materialização deve preservar uma versão identificável da escala planejada. O fechamento deve proteger essa versão contra alterações ordinárias. A reabertura deve obedecer à autorização, exigir justificativa e preservar o histórico anterior.

As operações de materialização, fechamento e reabertura deverão verificar as condições atuais no backend, evitando confirmar uma operação com base em informações desatualizadas.

A implementação deverá considerar operações atômicas para mudanças que precisem ocorrer em conjunto, especialmente quando houver alteração de estado, criação de versão e registro de auditoria.

## 8. Concorrência de edição

No MVP, cada escala poderá ter apenas um editor ativo por vez.

Outros usuários autorizados poderão consultar a escala, mas não poderão editar enquanto houver um bloqueio de edição válido.

O bloqueio deverá ser gerenciado pelo backend, com duração limitada, renovação e recuperação após perda de conexão ou encerramento inesperado da sessão. Não deverá existir bloqueio permanente causado pelo fechamento do navegador ou por uma falha de rede.

A solução deverá indicar quem está editando a escala. A arquitetura deve evitar impedir uma futura evolução para edição simultânea, sem implementar essa complexidade no MVP.

## 9. Desempenho

A edição da matriz mensal deve priorizar atualizações locais e validações incrementais quando possível.

A aplicação não deverá recalcular indiscriminadamente toda a escala a cada interação se for possível verificar apenas os elementos afetados.

Isso não dispensa uma validação completa e autoritativa no backend antes da materialização.

A interface também deverá tratar estados de salvamento, falha de conexão e alterações pendentes, sem indicar que uma alteração foi salva antes da confirmação do backend.

## 10. E-mail e notificações

O Escalar deverá utilizar notificações por e-mail para ativação de conta, recuperação de acesso e comunicação de publicação ou atualização de escalas, conforme as decisões funcionais do projeto.

O provedor de e-mail ainda deverá ser selecionado. A escolha dependerá de custo, limites de envio, segurança, confiabilidade e compatibilidade com o ambiente de hospedagem.

O envio deverá ser desacoplado da operação principal de fechamento: uma falha no envio de e-mail não deverá desfazer um fechamento confirmado. A arquitetura deverá permitir identificar e tratar falhas de notificação.

Links de acesso não deverão permitir consulta irrestrita ou pública às escalas individuais.

## 11. Testes e qualidade

Antes da implantação, deverão ser estabelecidas verificações automatizadas e procedimentos de validação para:

* Regras de negócio críticas.
* Permissões por papel e escopo.
* Integridade dos dados.
* Edição e salvamento da matriz.
* Materialização, fechamento e reabertura.
* Proteção de versões históricas.
* Acesso individual às escalas.
* Comportamento diante de falhas de rede e de persistência.
* Fluxos essenciais da interface.

O agente de desenvolvimento deverá implementar e executar os testes previstos e apresentar os resultados. Decisões de negócio não documentadas deverão ser encaminhadas para definição, e não inventadas durante a implementação.

## 12. Decisões técnicas pendentes

Os seguintes pontos deverão ser definidos antes da implementação correspondente:

1. Estrutura detalhada do projeto SvelteKit e organização dos módulos.
2. Estratégia de renderização e configuração final do build para a hospedagem escolhida.
3. Modelo relacional do banco, migrações e estratégia de versionamento do esquema.
4. Distribuição das regras entre aplicação, servidor e banco de dados.
5. Configuração das políticas RLS e demais controles de autorização.
6. Provedor e fluxo de envio de e-mails.
7. Política de backups, recuperação e retenção de dados.
8. Estratégia de logs, auditoria técnica e monitoramento.
9. Expiração de sessão e parâmetros de segurança.
10. Procedimento definitivo de integração e implantação.
11. Estratégia de testes automatizados e critérios mínimos de aprovação.
12. Verificação das limitações e dos custos vigentes dos serviços escolhidos.

Nenhum desses pontos autoriza a alteração unilateral das regras de negócio já aprovadas.

## 13. Diretriz final

A arquitetura do Escalar deverá ser a mais simples possível entre as alternativas que atendam aos requisitos de segurança, integridade, desempenho, auditoria e evolução do produto.

A adoção de novas tecnologias, serviços ou camadas deverá ser justificada por uma necessidade concreta.

**O planejamento técnico define como as regras aprovadas serão implementadas; não concede ao agente autonomia para redefinir essas regras.**
