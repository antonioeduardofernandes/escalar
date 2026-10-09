# Interface e experiência do usuário — Escalar

**Status:** planejamento de interface em andamento
**Produto:** Escalar — Sistema de Gestão de Escalas Hospitalares

## 1. Objetivo

Este documento estabelece as diretrizes de identidade visual, navegação, organização das telas, acessibilidade e interação do Escalar.

O sistema deverá ser moderno, institucional, discreto e eficiente. A interface deve favorecer a leitura de informações operacionais, a identificação de problemas e a execução segura das tarefas, sem sacrificar o desempenho.

As decisões visuais devem respeitar as regras de negócio documentadas. Uma escolha de interface não poderá alterar permissões, transformar um alerta em autorização ou permitir uma operação que as regras do sistema proíbam.

## 2. Princípios de experiência

1. **Clareza:** o usuário deve compreender o estado da escala, as pendências e as ações disponíveis.
2. **Eficiência:** tarefas recorrentes devem exigir o menor número razoável de interações.
3. **Consistência:** componentes e comportamentos semelhantes devem seguir os mesmos padrões.
4. **Feedback imediato:** toda interação relevante deve indicar seu resultado ou estado atual.
5. **Segurança operacional:** ações importantes devem apresentar contexto, validação e confirmação adequados.
6. **Acessibilidade:** informações importantes não podem depender exclusivamente de cores, ícones ou movimentos.
7. **Responsividade:** a interface deve se adaptar aos dispositivos previstos para cada perfil de uso.
8. **Desempenho:** animações e recursos visuais não devem prejudicar a leitura ou a velocidade de operação.
9. **Previsibilidade:** ações de salvamento, validação, materialização, fechamento e reabertura devem ser visualmente distintas.
10. **Respeito às permissões:** a interface deverá mostrar somente as ações compatíveis com o papel, o escopo e o estado atual, mantendo a autorização definitiva no backend.

## 3. Identidade visual

### 3.1. Direção estética

A identidade visual será sóbria e institucional contemporânea.

A base utilizará azul-marinho, branco e tons de cinza frio. Cores adicionais serão utilizadas com propósito funcional, especialmente para comunicar estados, alertas, conflitos e bloqueios.

A aparência deve evitar tanto o excesso de elementos decorativos quanto uma estética antiga, rígida ou visualmente carregada.

### 3.2. Paleta inicial

Os valores abaixo são referências iniciais, sujeitos à validação de contraste e legibilidade na interface real.

| Função                  | Cor            | Referência inicial |
| ----------------------- | -------------- | ------------------ |
| Identidade e navegação  | Azul-marinho   | `#172B4D`          |
| Ações e seleção         | Azul moderado  | `#356B9A`          |
| Superfícies secundárias | Cinza azulado  | `#E8EDF3`          |
| Conteúdo principal      | Branco         | `#FFFFFF`          |
| Situação válida         | Verde suave    | `#DCEFE3`          |
| Atenção                 | Amarelo suave  | `#FFF0BF`          |
| Conflito relevante      | Laranja suave  | `#FCE2CF`          |
| Bloqueio                | Vermelho suave | `#F9DEDE`          |

Os fundos dos estados poderão ser suaves, com textos, bordas e ícones em tons suficientemente contrastantes. As cores finais deverão ser verificadas nos componentes reais, incluindo texto, ícones, foco, seleção e mensagens de erro.

### 3.3. Cores semânticas

As cores deverão comunicar significados consistentes em todos os módulos.

* **Verde:** situação válida ou operação concluída sem pendências relevantes.
* **Amarelo:** atenção, informação incompleta ou necessidade de conferência.
* **Laranja:** conflito ou inconsistência relevante que exige análise ou correção conforme a regra aplicável.
* **Vermelho:** impedimento, violação de regra bloqueante ou ação proibida.
* **Azul:** ação principal, seleção, navegação ou informação institucional, conforme o componente.

A cor representa o resultado da regra de negócio correspondente. Não deverá ser utilizada para inventar uma gravidade que não esteja definida.

Alertas que exigem análise não equivalem automaticamente a bloqueios. Restrições impeditivas não podem ser ignoradas apenas porque o usuário compreendeu ou confirmou uma mensagem.

A classificação operacional de cada situação será determinada pelas regras de negócio, não por uma escolha estética.

### 3.4. Uso de cores na matriz

A diferenciação dos turnos e os indicadores de conflitos deverão ser visualmente compatíveis.

A célula deve privilegiar o código do turno e a leitura rápida. Alertas poderão utilizar ícones, bordas ou indicadores próprios, sem necessariamente substituir a cor de identificação do turno.

Toda situação importante deverá ter complemento textual, código ou ícone compreensível. A interface não deverá depender exclusivamente da percepção das cores.

## 4. Componentes visuais

A base da interface utilizará:

* Tailwind CSS para estilização e responsividade.
* shadcn-svelte para componentes reutilizáveis e personalizáveis.
* Lucide Icons para ícones.

Os componentes deverão manter padrões consistentes de dimensões, espaçamentos, tipografia, bordas, estados de foco, mensagens e comportamento.

A matriz de escalas poderá utilizar componentes próprios, pois suas necessidades de edição, navegação e desempenho são específicas.

Componentes compartilhados deverão evitar que cada módulo implemente sua própria versão de botões, formulários, diálogos, mensagens de erro ou indicadores de estado sem justificativa.

## 5. Estrutura principal da aplicação

### 5.1. Cabeçalho

O cabeçalho deverá ser compacto e disponibilizar os elementos globais necessários, como:

* Identidade do Escalar.
* Controle do menu lateral.
* Unidade selecionada, quando aplicável.
* Notificações, quando implementadas.
* Identificação do usuário e acesso às opções da conta.

O cabeçalho não deverá acumular ações operacionais específicas de cada módulo.

### 5.2. Menu lateral recolhível

O menu lateral será persistente nas telas administrativas.

No desktop, ficará expandido por padrão e poderá ser recolhido para liberar espaço horizontal.

Quando recolhido, deverá preservar a navegação por ícones, com identificação acessível e dicas visuais de contexto. O estado recolhido não poderá impedir a navegação por teclado ou a compreensão das opções disponíveis.

O menu deverá:

* Apresentar os módulos de forma organizada.
* Exibir opções conforme o papel e o escopo autorizado.
* Indicar claramente a seção atual.
* Evitar excesso de níveis de navegação.
* Manter comportamento consistente entre os módulos.

A ocultação de opções no menu é uma decisão de experiência, não um mecanismo de segurança. O backend continuará responsável por aplicar as permissões.

### 5.3. Área central

A área central será destinada ao conteúdo do módulo selecionado.

Cada tela deverá priorizar seu objetivo principal, evitando painéis, cartões e informações secundárias que reduzam desnecessariamente o espaço útil.

### 5.4. Painel lateral de resumo

Na tela de elaboração de escalas, haverá um painel de resumo à direita da matriz.

Esse painel poderá ser recolhido independentemente do menu principal.

Deverá apresentar, conforme o estado da escala:

* Completude e pendências.
* Células vazias relevantes.
* Conflitos impeditivos e alertas.
* Horas planejadas em turnos ordinários.
* Informações de APH separadas.
* Cobertura planejada em comparação com o dimensionamento.
* Ações pendentes e resultados de validação.

Quando possível, a seleção de um indicador deverá conduzir o usuário à célula ou ao ponto relevante da matriz.

O painel não deverá transformar um indicador resumido em autorização para ignorar uma regra impeditiva.

## 6. Experiência por perfil e dispositivo

### 6.1. Desktop

O desktop será o ambiente principal para as atividades administrativas e operacionais completas.

Deverá suportar:

* Elaboração e edição de escalas.
* Aplicação de modelos e ajuste de exceções.
* Gestão de equipes e modelos.
* Registro de ocorrências e compensações.
* Dimensionamento.
* Validação, materialização e fechamento.
* Consultas e relatórios.

A matriz deverá aproveitar a largura disponível, com controles de rolagem e painéis que possam ser recolhidos quando necessário.

### 6.2. Tablet

No MVP, o tablet será voltado prioritariamente à consulta e conferência de escalas.

A interface deverá favorecer a legibilidade, a identificação de conflitos e a navegação pelos registros. A elaboração completa de escalas no tablet não faz parte do escopo inicial.

Funcionalidades de conferência mais avançadas poderão ser desenvolvidas posteriormente, conforme a documentação de projetos futuros.

### 6.3. Smartphone

No MVP, o smartphone terá uma experiência simplificada, centrada na consulta individual do servidor.

A interface deverá:

* Abrir diretamente a escala individual após a autenticação.
* Exibir apenas as informações às quais o servidor tem direito de acesso.
* Priorizar a leitura em telas pequenas.
* Disponibilizar download opcional de PDF, quando implementado.
* Evitar menus administrativos e ferramentas de edição de escala.

A interface móvel não deverá ser uma simples versão comprimida da matriz administrativa.

O link recebido por e-mail deverá conduzir a um fluxo seguro de autenticação e, após o acesso válido, encaminhar o servidor à própria escala. O link não deverá funcionar como autorização pública e irrestrita.

## 7. Painel operacional inicial

A tela inicial dos perfis administrativos será um painel operacional, adaptado ao papel e ao escopo do usuário.

O painel poderá apresentar:

* Situação das escalas sob responsabilidade do usuário.
* Pendências que exigem atenção.
* Conflitos relevantes.
* Atalhos para tarefas frequentes.
* Informações de contexto da unidade selecionada.

O conteúdo não será idêntico para todos os papéis. O Gestor, o Supervisor e o Administrador deverão visualizar informações compatíveis com suas responsabilidades.

Os dados apresentados deverão refletir o estado real do sistema. Indicadores ilustrativos não deverão aparecer como dados reais na aplicação operacional.

A mudança da unidade selecionada deverá atualizar os dados exibidos conforme o escopo autorizado. Ela não poderá ampliar permissões nem expor dados de outras unidades.

## 8. Navegação e módulos

A organização inicial proposta para a navegação será:

### Visão geral

Painel operacional e pendências.

### Estrutura organizacional

* Servidores.
* Unidades.
* Equipes e modelos.

### Operação

* Escalas.
* Ocorrências e compensações.
* Dimensionamento.

### Consultas

* Relatórios.
* Consultas históricas disponíveis conforme as permissões.

### Administração

* Cargos e vínculos institucionais.
* Usuários, papéis e permissões.
* Configurações administrativas.

A composição exata dos menus será condicionada aos papéis e escopos autorizados. O perfil Servidor terá uma navegação própria e simplificada.

### 8.1. Restrições por perfil

A interface deverá respeitar as permissões já definidas nas regras de negócio.

* **Administrador:** mantém configurações, cargos, vínculos institucionais, acessos e permissões. Não recebe automaticamente autorização para materializar, fechar ou reabrir escalas.
* **Gestor:** executa operações de gestão de escalas dentro do escopo autorizado. Não pode criar, editar, desativar ou reativar cadastros de servidores.
* **Supervisor:** executa as operações autorizadas no seu escopo, incluindo reabertura de escalas fechadas e manutenção das datas institucionais adicionais permitidas pelas regras do projeto.
* **Servidor:** consulta sua própria escala e utiliza apenas as funções individuais autorizadas.

Somente Administrador e Supervisor poderão criar, editar, desativar ou reativar cadastros de servidores, respeitando o escopo do Supervisor.

A gestão de cargos e vínculos institucionais será exclusiva do Administrador.

Os nomes e agrupamentos dos menus não alteram essas permissões. A Divisão de Enfermagem é uma unidade organizacional, não um papel adicional.

## 9. Matriz de elaboração de escalas

### 9.1. Organização

A tela principal de elaboração será uma matriz mensal:

* Cada linha representa um servidor.
* Cada coluna representa um dia do mês.
* A primeira coluna identifica o servidor e permanece fixa durante a rolagem horizontal.
* O cabeçalho das datas permanece visível durante a rolagem vertical.

A interface deverá suportar rolagem horizontal e vertical sem perder a referência entre servidores e datas.

### 9.2. Cabeçalho operacional

A parte superior da tela deverá apresentar:

* Unidade e contexto de trabalho.
* Mês e ano selecionados.
* Navegação para mês anterior e próximo.
* Seleção do período.
* Estado atual da escala.
* Ações disponíveis conforme papel, escopo e estado.

A mudança de mês ou contexto não poderá modificar dados existentes silenciosamente.

### 9.3. Criação de uma nova escala mensal

Ao iniciar uma nova escala mensal, o sistema deverá sugerir o preenchimento com base nos modelos válidos para o período.

A escala do mês anterior poderá ser consultada como referência para comparação, mas **não deverá ser copiada automaticamente**.

A aplicação de modelos deverá apresentar uma prévia quando houver possibilidade de substituir turnos existentes. O padrão será preencher células vazias; a substituição de conteúdo exigirá revisão e confirmação explícitas.

A sugestão baseada em modelos não elimina a necessidade de validação das regras aplicáveis.

### 9.4. Células e turnos

As células deverão exibir de forma compacta o código do turno, como SD, SN, DN, M, T ou APH.

O horário completo não deverá ocupar permanentemente todas as células. Os detalhes estarão disponíveis ao selecionar a célula ou abrir o painel correspondente.

A identificação visual dos turnos deverá ser acompanhada de legenda consistente.

Os turnos ordinários e o APH deverão ser visualmente distinguíveis. Essa diferenciação visual não poderá alterar a contabilização de horas ou os critérios de cobertura definidos nas regras de negócio.

A referência de 120 horas mensais não deverá ser apresentada como meta universal: aplica-se ao planejamento ordinário dos plantonistas conforme as regras do projeto, não aos diaristas nem ao APH.

### 9.5. Edição rápida e painel de detalhes

A edição dos turnos seguirá o modelo de edição rápida na célula, com painel de detalhes quando necessário.

Ao selecionar uma célula editável, o usuário poderá escolher o turno de maneira compacta.

O painel de detalhes poderá apresentar:

* Servidor e data.
* Turno e horário.
* Informações relevantes para a operação.
* Conflitos e explicações das regras envolvidas.
* Ações permitidas para aquela situação.

A interface deverá distinguir ações indisponíveis por permissão, por estado da escala ou por violação de regra.

A escolha de um turno deverá disparar as verificações pertinentes e apresentar o resultado. A gravação definitiva continuará sujeita à validação do backend.

### 9.6. Filtros

A matriz deverá permitir combinar filtros, incluindo, conforme aplicável:

* Equipe.
* Cargo.
* Situação do preenchimento.
* Conflitos e alertas.
* Busca por nome ou matrícula.

Os filtros combinados deverão ser aplicados de forma consistente. A interface deverá indicar os filtros ativos, a quantidade de resultados e oferecer remoção individual ou limpeza de todos os filtros.

Uma linha ou célula ocultada por filtros não poderá ser interpretada como vazia ou excluída.

Os filtros não poderão ampliar o escopo de acesso aos dados.

### 9.7. Resumo e indicadores

O painel de resumo deverá consolidar informações operacionais relevantes e permitir navegação até os pontos que exigem atenção.

As horas de turnos ordinários e de APH deverão ser apresentadas separadamente, inclusive quando houver um total consolidado.

Os indicadores de cobertura deverão respeitar os critérios de elegibilidade e dimensionamento definidos nas regras de negócio.

Alertas, conflitos, cobertura insuficiente e células vazias deverão ser apresentados como situações distintas quando tiverem significados ou consequências diferentes.

### 9.8. Salvamento

A interface deverá comunicar claramente os estados:

* Salvo.
* Salvando.
* Alterações pendentes.
* Falha ao salvar.

O estado “Salvo” só poderá ser apresentado após a confirmação da persistência pelo backend.

Falhas de rede ou de gravação não poderão causar perda silenciosa de alterações. O sistema deverá informar o problema e preservar as alterações pendentes sempre que tecnicamente possível.

O salvamento automático não equivale à validação completa, à materialização ou ao fechamento da escala.

### 9.9. Edição exclusiva

No MVP, somente um usuário poderá editar uma escala por vez.

Quando houver bloqueio ativo, outros usuários autorizados poderão consultar a escala, mas não editá-la. A interface deverá indicar quem está com a edição ativa e comunicar quando o acesso de edição estiver indisponível.

O bloqueio deverá ser temporário e gerenciado pelo backend.

### 9.10. Validação e transições de estado

A interface poderá realizar validações incrementais para oferecer retorno rápido durante a edição.

Antes da materialização, deverá haver uma validação completa e autoritativa no backend.

O sistema deverá distinguir:

* Situações válidas.
* Alertas que exigem análise.
* Conflitos impeditivos.
* Pendências que exigem preenchimento ou revisão.

A classificação deverá respeitar as regras de negócio. A cor de um alerta não poderá, por si só, autorizar ou impedir a operação.

Se a escala for modificada depois de uma validação completa, o resultado anterior deverá ser considerado desatualizado.

As ações de materialização, fechamento e reabertura deverão aparecer conforme as permissões e o estado da escala. O fechamento exigirá confirmação explícita. A reabertura deverá solicitar justificativa e preservar o histórico.

### 9.11. Desfazer e refazer

A experiência deverá permitir desfazer e refazer múltiplas alterações durante a edição, conforme a implementação definida.

Esses recursos não poderão apagar o histórico oficial de auditoria, modificar versões fechadas diretamente ou contornar as regras de materialização e reabertura.

A interface deverá deixar claro quando uma alteração ainda não foi salva. Operações que já tenham produzido efeitos persistentes deverão respeitar as regras de recuperação e auditoria, não sendo tratadas como se nunca tivessem ocorrido.

## 10. Feedback, confirmação e recuperação

Ações relevantes deverão apresentar feedback claro e oportuno.

A interface deverá evitar mensagens genéricas que não expliquem o resultado. Quando uma operação for recusada, deverá informar o motivo de forma útil, sem expor detalhes internos sensíveis.

Operações potencialmente destrutivas ou que alterem versões oficiais deverão apresentar confirmação adequada.

A confirmação do usuário não poderá substituir uma permissão ausente ou permitir uma operação proibida pelas regras de negócio.

Em falhas de conexão ou persistência, a interface deverá informar o estado e preservar alterações pendentes sempre que tecnicamente possível.

## 11. Acessibilidade e movimento

A interface deverá observar:

* Contraste suficiente entre texto, fundo e controles.
* Navegação por teclado nos elementos interativos.
* Estados de foco visíveis.
* Identificação textual de alertas e bloqueios.
* Rótulos acessíveis para ícones e controles.
* Mensagens claras de erro e sucesso.
* Respeito à preferência por redução de movimento.

Transições e animações poderão ser utilizadas de maneira discreta para comunicar mudanças de estado, abrir painéis e confirmar interações. Não deverão ser essenciais para compreender uma operação.

As cores semânticas deverão ser verificadas quanto ao contraste, especialmente quando usadas em textos pequenos, indicadores ou bordas.

## 12. Responsividade e desempenho

A interface deverá ser testada em diferentes resoluções e escalas de tela, especialmente nas áreas de maior densidade de informação.

A responsividade não deverá resultar em controles sobrepostos, textos ilegíveis ou perda de contexto da matriz.

A aplicação deverá priorizar atualizações localizadas e evitar animações, renderizações ou cálculos desnecessários durante a edição.

O comportamento específico para desktop, tablet e smartphone deverá seguir as responsabilidades definidas neste documento, em vez de tentar oferecer todas as funções em todos os dispositivos.

A matriz deverá ser validada com volumes representativos de servidores e dias, utilizando dados fictícios, para verificar legibilidade, rolagem e tempo de resposta.

## 13. Publicação e consulta individual

O fechamento de uma escala deverá dar início ao fluxo de publicação e notificação previsto nas regras do projeto.

A interface deverá comunicar o fechamento com base na confirmação do backend. O envio de e-mails deverá ser tratado separadamente, para que uma falha de notificação não seja apresentada como falha do fechamento já confirmado.

Após a publicação, o servidor deverá receber um e-mail com um link seguro para consulta.

O sistema não deverá enviar PDFs automaticamente como anexos. O servidor poderá acessar a própria escala após autenticação e baixar o PDF opcionalmente, quando esse recurso estiver implementado.

Quando uma escala for reaberta e uma nova versão for posteriormente fechada e publicada, o histórico deverá ser preservado no sistema. A interface individual deverá apresentar a versão atual autorizada, sem exigir que o servidor gerencie manualmente as versões anteriores.

## 14. Critérios gerais de aceitação visual e funcional

A interface será considerada alinhada a estas diretrizes quando:

1. A navegação administrativa for consistente e recolhível.
2. O contexto da unidade e o estado da escala forem identificáveis.
3. A matriz mantiver as referências de servidores e datas durante a rolagem.
4. Turnos, alertas e bloqueios forem distinguíveis sem depender exclusivamente das cores.
5. A edição rápida e o painel de detalhes apresentarem as informações necessárias à decisão.
6. O usuário conseguir identificar se há alterações pendentes ou falha de salvamento.
7. Ações operacionais respeitarem papel, escopo e estado da escala.
8. A mudança de unidade não ampliar permissões nem expor dados não autorizados.
9. A interface móvel permitir consulta individual segura e legível.
10. O sistema distinguir salvamento, validação, materialização, fechamento e publicação.
11. A falha de envio de e-mail não for confundida com falha de fechamento já confirmado.
12. Os elementos mantiverem consistência de tipografia, espaçamento, ícones e comportamento.
13. A experiência continuar utilizável com redução de movimento e navegação por teclado.
14. A classificação visual dos estados corresponder às regras de negócio.
15. O desempenho da matriz for aceitável com dados fictícios representativos.

## 15. Pendências para detalhamento posterior

Antes da implementação das telas correspondentes, deverão ser detalhados:

* Wireframes das principais telas administrativas.
* Composição exata dos indicadores do painel operacional por papel.
* Especificação visual dos turnos e dos alertas na matriz.
* Comportamento da matriz em resoluções menores.
* Conteúdo e hierarquia do painel de resumo.
* Componentes reutilizáveis e seus estados.
* Fluxos de confirmação e mensagens de erro.
* Especificação visual da consulta individual e do PDF.
* Testes de acessibilidade e contraste.
* Critérios de desempenho para a matriz.
* Comportamentos visuais dos estados de salvamento, bloqueio de edição e falha de conexão.

Esses detalhamentos deverão respeitar as decisões aprovadas e não alterar regras de negócio por conveniência visual.

## 16. Diretriz final

A interface do Escalar deve ajudar o usuário a compreender o estado operacional e agir com segurança, sem esconder informações relevantes nem sobrecarregar a tela.

A estética deve servir à clareza e à eficiência. O comportamento deve ser previsível, os estados devem ser explícitos e as regras de negócio devem continuar sendo a autoridade sobre as operações permitidas.
