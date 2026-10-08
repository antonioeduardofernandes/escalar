# Escalar — Permissões e Papéis

## 1. Princípio geral

As permissões do Escalar devem ser definidas por:

* papel do usuário;
* âmbito de atuação;
* unidade/setor ao qual o acesso está vinculado;
* autorização específica, quando aplicável.

Não se deve assumir que todo usuário possui acesso global ao sistema.

O fato de um usuário possuir acesso a determinado setor não implica, automaticamente, acesso aos demais setores.

---

## 2. Administrador

O Administrador é responsável pelo gerenciamento estrutural e administrativo do sistema.

Pode, conforme as funcionalidades administrativas previstas:

* cadastrar unidades/setores;
* editar unidades/setores;
* desativar unidades/setores;
* cadastrar usuários;
* administrar perfis e permissões;
* manter configurações administrativas do sistema.

O Administrador atua sobre a estrutura do sistema e não deve receber automaticamente responsabilidades operacionais de gestão de escalas apenas por possuir o papel administrativo.

As permissões administrativas detalhadas devem ser definidas conforme cada módulo do sistema.

---

## 3. Supervisor

O Supervisor possui responsabilidade operacional sobre o cadastro e a manutenção dos servidores.

Pode:

* criar servidores;
* editar servidores;
* corrigir dados cadastrais;
* inativar servidores;
* reativar servidores.

As alterações devem respeitar as regras de cadastro e imutabilidade definidas em `02-regras-de-negocio.md` e detalhadas em `04-cadastros-e-lotacoes.md`.

O acesso do Supervisor deve respeitar o âmbito de atuação definido para o usuário.

---

## 4. Enfermeira de rotina

A Enfermeira de rotina é responsável pela operação cotidiana da escala dentro de seu âmbito de atuação.

Pode:

* consultar a escala;
* realizar alterações na escala;
* realizar ajustes operacionais;
* trabalhar sobre as escalas dos setores para os quais possui autorização.

O acesso não deve ser considerado global por padrão.

As ações permitidas devem respeitar o estado da escala, incluindo as restrições existentes após o fechamento.

---

## 5. Secretário

O Secretário atua como **assessoria do enfermeiro responsável**.

O Secretário não é considerado gestor da escala.

Seu acesso pode ser delegado pelo enfermeiro responsável, dentro do âmbito autorizado.

O Secretário pode operar as funcionalidades da escala que lhe forem delegadas.

A delegação não deve conceder automaticamente permissões administrativas ou de gestão que não façam parte do acesso delegado.

As regras detalhadas de delegação e de seus limites devem ser definidas antes da implementação dessa funcionalidade.

---

## 6. Divisão de Enfermagem

A Divisão de Enfermagem possui responsabilidade ampla sobre a gestão das escalas e sobre determinadas alterações estruturais relacionadas à lotação.

Entre suas responsabilidades estão:

* controlar lotações;
* realizar alterações de lotação;
* controlar alterações posteriores ao fechamento;
* autorizar ou liberar alterações em escalas fechadas quando necessário;
* acompanhar a situação das escalas sob sua responsabilidade.

A Divisão de Enfermagem possui sua própria escala.

As ações da Divisão devem preservar a rastreabilidade das alterações realizadas.

---

## 7. Acesso a múltiplos setores

Um usuário pode possuir autorização para atuar em mais de uma unidade/setor quando isso fizer parte de sua responsabilidade.

O acesso deve estar vinculado explicitamente aos setores autorizados.

Possuir acesso a um setor não concede automaticamente acesso a todos os demais.

A possibilidade de um mesmo usuário possuir diferentes papéis ou diferentes âmbitos de atuação deve ser definida antes da implementação caso seja necessária ao funcionamento do sistema.

---

## 8. Âmbito de atuação

O papel define **o que o usuário pode fazer**.

O âmbito de atuação define **onde o usuário pode fazer**.

Essas duas dimensões devem ser consideradas separadamente.

Exemplo conceitual:

> Um usuário pode possuir permissão para operar escalas, mas somente nos setores para os quais possui autorização.

O sistema não deve ampliar automaticamente o âmbito de atuação apenas porque o usuário possui determinado papel.

---

## 9. Escalas fechadas

O acesso a uma escala fechada deve respeitar as regras de fechamento e as permissões correspondentes.

Alterações posteriores ao fechamento não devem ser tratadas como uma alteração operacional comum.

Quando uma alteração posterior for autorizada, ela deve respeitar as regras de rastreabilidade e auditoria.

A Divisão de Enfermagem possui responsabilidade sobre o controle dessas alterações.

As regras detalhadas de fechamento e alteração posterior devem ser definidas em `09-fechamento-e-auditoria.md`.

---

## 10. Princípio de menor privilégio

Um usuário deve possuir somente as permissões necessárias para exercer sua responsabilidade no sistema.

Não se deve conceder acesso administrativo apenas para permitir que uma operação específica seja executada.

O sistema deve representar a responsabilidade real do usuário por meio de permissões adequadas.

---

## 11. Regra para implementação

O agente não deve transformar um papel operacional em administrador ou conceder permissões adicionais apenas para facilitar uma implementação.

Quando uma funcionalidade exigir uma permissão que ainda não esteja definida, a lacuna deve ser identificada e submetida à definição do produto.

O agente não deve criar uma nova responsabilidade de negócio para resolver uma limitação técnica.

---

## 12. Pendências de definição

As seguintes decisões devem ser definidas antes da implementação dos respectivos recursos:

* quem possui permissão para materializar uma escala;
* quem possui permissão para fechar uma escala;
* se materialização e fechamento podem ser realizados pelo mesmo papel;
* quais ações podem ser realizadas por cada papel antes da materialização;
* quais ações podem ser realizadas após a materialização e antes do fechamento;
* quais ações podem ser realizadas após o fechamento;
* como funciona exatamente a delegação de acesso do Secretário;
* se um usuário pode possuir mais de um papel simultaneamente;
* como permissões específicas podem ser concedidas dentro de um mesmo papel;
* quais ações administrativas exigem rastreabilidade;
* como será definido o âmbito de atuação de usuários que trabalham em múltiplos setores.

Essas pendências não devem ser resolvidas por suposição durante a implementação.

---

## 13. Regra para agentes

Os papéis e permissões documentados neste arquivo constituem regras funcionais do Escalar.

O agente não deve:

* criar novos papéis sem aprovação;
* ampliar permissões de um papel existente por conveniência técnica;
* transformar um usuário operacional em administrador para contornar restrições;
* assumir acesso global quando o âmbito não estiver definido;
* criar regras de delegação não documentadas.

Quando uma permissão necessária não estiver definida, a implementação deve ser interrompida nessa parte e a decisão deve ser submetida à definição do produto.
