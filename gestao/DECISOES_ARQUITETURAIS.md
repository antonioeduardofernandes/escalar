# Decisões Arquiteturais — Escalar

## 1. Finalidade

Este documento registra decisões arquiteturais relevantes para o desenvolvimento do Escalar, incluindo contexto, alternativas consideradas, decisão tomada, justificativa, consequências e status.

Seu objetivo é preservar a fundamentação das escolhas técnicas, evitar que decisões sejam reabertas desnecessariamente e permitir que o desenvolvimento continue de forma consistente entre sessões de trabalho.

O registro deve conter decisões verificáveis e relevantes para a arquitetura. Não deve ser utilizado como substituto da documentação de requisitos ou das regras de negócio.

## 2. Convenção de registro

Cada decisão deve possuir um identificador estável, no formato `ADR-NNN`, em que `NNN` é uma sequência numérica.

Depois de publicado, o identificador não deve ser reutilizado, mesmo que a decisão seja posteriormente substituída ou revogada.

### Estrutura de cada decisão

* **Identificador:** código único da decisão.
* **Título:** resumo objetivo.
* **Status:** situação atual.
* **Contexto:** problema ou necessidade que motivou a decisão.
* **Decisão:** solução efetivamente aprovada.
* **Justificativa:** motivos que fundamentam a escolha.
* **Consequências:** impactos positivos, limitações, riscos e dependências.
* **Documentos relacionados:** arquivos que registram requisitos ou detalhes associados.
* **Histórico:** alterações de status, revisões e substituições.

## 3. Status possíveis

* **Proposta:** alternativa sugerida, ainda sem aprovação.
* **Aprovada:** decisão confirmada pelo responsável pelo projeto.
* **Substituída:** decisão que deixou de vigorar e foi substituída por outra.
* **Rejeitada:** alternativa avaliada e explicitamente rejeitada.
* **Pendente:** decisão necessária, mas ainda sem resolução.

Uma tecnologia descrita em um documento não deve ser automaticamente considerada uma decisão aprovada. É necessário verificar se ela foi efetivamente estabelecida como decisão do projeto.

## 4. Registro de decisões

### ADR-001 — Separação entre especificação do sistema e gestão do projeto

**Status:** Aprovada.

**Contexto**

O projeto precisa manter, de um lado, os requisitos e as especificações que orientam o comportamento esperado do sistema e, de outro, os registros de acompanhamento utilizados para preservar o contexto e organizar o trabalho entre sessões.

Manter essas finalidades misturadas dificulta a manutenção e a retomada do planejamento.

**Decisão**

Organizar a documentação em duas áreas:

* `docs/`: documentação de especificação funcional e técnica do sistema.
* `gestao/`: documentação de acompanhamento e continuidade do projeto.

O `README.md` permanece na raiz como porta de entrada do repositório.

**Justificativa**

A separação distingue a especificação do produto do registro mutável de progresso, pendências e decisões, facilitando a consulta e a manutenção.

**Consequências**

* Os documentos de especificação continuam sendo a referência para requisitos e implementação.
* Os documentos de gestão passam a registrar a situação do trabalho e facilitar a retomada entre conversas.
* Links e referências devem ser revisados sempre que documentos forem movidos.
* A mudança de organização não autoriza alterar silenciosamente regras de negócio existentes.

**Documentos relacionados**

* `README.md`
* `gestao/ESTADO_DO_PROJETO.md`
* `gestao/INDICE_DOCUMENTACAO.md`
* `docs/`

**Histórico**

* Registro inicial da decisão de organização documental.

## 5. Decisões ainda não registradas

Não devem ser criadas decisões arquiteturais fictícias para preencher este documento.

As decisões técnicas existentes precisam ser identificadas a partir da documentação do projeto e, quando necessário, confirmadas pelo responsável.

Até que essa revisão seja realizada, não se deve presumir que linguagens, frameworks, banco de dados, infraestrutura, mecanismos de autenticação ou outras tecnologias estejam aprovados apenas porque foram mencionados em discussões ou propostas.

## 6. Como registrar novas decisões

Quando uma decisão arquitetural for aprovada:

1. Identificar o problema que precisa ser resolvido.
2. Registrar o contexto e as alternativas relevantes.
3. Documentar a decisão efetivamente aprovada.
4. Explicar a justificativa e as consequências.
5. Referenciar os requisitos e documentos afetados.
6. Avaliar se outros documentos precisam ser atualizados.
7. Atualizar o estado do projeto quando houver impacto no progresso, nos riscos ou na próxima ação.

Quando uma decisão existente for alterada, preservar seu identificador e seu histórico. Se outra decisão a substituir, registrar a relação entre os dois identificadores.

## 7. Relação com as regras de negócio

As regras de negócio devem permanecer nos documentos de especificação correspondentes.

Uma decisão arquitetural pode referenciar uma regra de negócio quando ela influenciar a arquitetura, mas não deve duplicar todo o conteúdo da regra.

As responsabilidades operacionais e as responsabilidades técnicas devem permanecer claramente diferenciadas, especialmente nos processos de fechamento e auditoria das escalas.

## 8. Histórico do documento

| Data        | Alteração                                              |
| ----------- | ------------------------------------------------------ |
| A registrar | Criação inicial do registro de decisões arquiteturais. |

As datas e as revisões futuras devem refletir alterações efetivamente realizadas.
