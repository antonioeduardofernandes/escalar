# Escalar — Equipes e Modelos

## 1. Objetivo

Equipes e modelos existem para facilitar a construção e o planejamento das escalas.

São mecanismos auxiliares de organização e planejamento e não substituem a escala efetivamente definida e materializada.

---

## 2. Equipes

Uma equipe representa um agrupamento estruturado de servidores utilizado para facilitar a organização e a composição das escalas.

Uma equipe pode ser utilizada para:

* organizar servidores;
* facilitar a seleção de servidores durante o planejamento;
* apoiar a aplicação de modelos;
* facilitar a visualização e a gestão da escala.

A equipe não substitui a lotação do servidor.

A participação de um servidor em uma equipe não altera automaticamente:

* sua matrícula;
* seu cargo;
* seu vínculo;
* seu regime;
* sua lotação;
* sua escala materializada.

---

## 3. Modelos

Um modelo representa um padrão utilizado para auxiliar a construção de uma escala.

O modelo pode conter uma configuração de jornadas e/ou alocações que possa ser utilizada como referência durante o planejamento.

A aplicação de um modelo deve ocorrer dentro das regras de jornada, lotação, regime e demais regras de negócio aplicáveis.

Um modelo não pode criar uma alocação que viole uma regra obrigatória do sistema.

---

## 4. Aplicação de equipes e modelos

Equipes e modelos podem ser utilizados durante o planejamento da escala.

A aplicação pode servir como ponto inicial para a composição da escala, permitindo que o responsável realize os ajustes necessários antes da materialização.

A aplicação automática de uma equipe ou modelo não significa que o resultado esteja definitivamente aprovado.

O responsável pela escala deve poder revisar e ajustar o resultado antes da materialização.

---

## 5. Alterações após a aplicação

A aplicação de uma equipe ou modelo não impede alterações manuais posteriores durante o planejamento.

O resultado final pode ser diferente do modelo originalmente utilizado.

A escala materializada representa a decisão final para aquele período, independentemente do modelo ou equipe que tenha sido utilizado durante sua construção.

---

## 6. Vigência e histórico

Equipes e modelos podem ser alterados ao longo do tempo.

Alterações posteriores em equipes ou modelos não devem reescrever automaticamente escalas de períodos anteriores que já tenham sido materializadas.

Quando necessário, deve ser possível identificar qual configuração estava sendo utilizada durante o planejamento da escala.

A alteração de uma equipe ou modelo não deve apagar o histórico das configurações anteriores quando esse histórico for relevante para rastreabilidade.

---

## 7. Relação com servidores

A utilização de uma equipe ou modelo não cria um novo servidor nem altera a identidade do servidor.

O servidor continua identificado por sua matrícula.

Alterações na composição de uma equipe não devem criar, excluir ou duplicar registros de servidores.

---

## 8. Relação com lotação

Equipes e modelos não substituem a lotação do servidor.

A aplicação de uma equipe ou modelo deve respeitar a lotação vigente e as regras de alocação.

Uma equipe ou modelo não pode, por si só, autorizar a alocação de um servidor em setor incompatível com sua lotação.

Atuações excepcionais em outro setor devem seguir as regras de APH quando aplicáveis.

---

## 9. Relação com regime e jornadas

A aplicação de um modelo deve respeitar o regime do servidor e as regras de jornadas definidas em `05-escalas-e-plantoes.md`.

Um modelo não pode:

* criar jornada de 36 horas;
* gerar intervalo inferior a 12 horas;
* criar jornada não autorizada;
* ignorar restrições obrigatórias de regime ou lotação.

Quando uma configuração do modelo entrar em conflito com uma regra obrigatória, a regra de negócio prevalece.

---

## 10. Materialização

A escala final materializada prevalece sobre o modelo utilizado para sua geração.

Depois da materialização, o modelo não deve ser utilizado para reescrever automaticamente a escala daquele período.

Alterações posteriores no modelo não devem modificar uma escala materializada.

Da mesma forma, alterar uma escala materializada não deve alterar automaticamente o modelo que foi utilizado para construí-la.

---

## 11. Automação

A aplicação automática de equipes e modelos é um mecanismo de apoio à decisão.

O sistema pode:

* sugerir uma composição;
* preencher uma escala com base em um modelo;
* identificar incompatibilidades;
* indicar conflitos;
* facilitar ajustes.

O sistema não deve considerar uma sugestão automaticamente aprovada apenas porque foi gerada por um modelo.

A decisão do responsável pela escala deve prevalecer, desde que respeitadas as regras obrigatórias do sistema.

---

## 12. Histórico e rastreabilidade

Quando uma equipe ou modelo for utilizado na construção de uma escala, o sistema deve preservar, quando aplicável, informações suficientes para permitir a rastreabilidade da origem da configuração utilizada.

A rastreabilidade deve permitir distinguir:

* configuração utilizada no planejamento;
* ajustes realizados posteriormente;
* resultado final materializado.

A existência de um modelo utilizado na construção não substitui o registro da decisão efetivamente materializada.

---

## 13. Regra para agentes

O agente de desenvolvimento deve tratar equipes e modelos como mecanismos auxiliares de planejamento.

O agente não deve:

* transformar modelo em regra permanente do servidor;
* alterar escala materializada automaticamente após mudança de modelo;
* alterar lotação por causa da aplicação de uma equipe;
* criar novos servidores por alteração de equipe;
* considerar automaticamente uma sugestão como decisão aprovada;
* inventar regras de aplicação ou prioridade não definidas.

Quando o comportamento de uma equipe ou modelo não estiver definido, o agente deve identificar a pendência em vez de criar uma regra própria.

---

## 14. Relação com outros documentos

As regras de equipes e modelos devem ser consideradas em conjunto com:

* `02-regras-de-negocio.md` — regras transversais;
* `03-permissoes-e-papeis.md` — permissões para criação e utilização;
* `04-cadastros-e-lotacoes.md` — servidores, lotações e regimes;
* `05-escalas-e-plantoes.md` — jornadas e materialização;
* `08-dimensionamento.md` — cobertura e dimensionamento;
* `09-fechamento-e-auditoria.md` — fechamento e rastreabilidade.

Regras específicas ainda não definidas devem ser decididas antes da implementação.
