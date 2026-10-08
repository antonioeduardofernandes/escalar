# Escalar — Fechamento e Auditoria

## 1. Objetivo

O fechamento encerra o ciclo operacional da escala daquele período e transforma a escala em uma referência consolidada para consulta e histórico.

O fechamento não apaga a materialização anterior da escala.

---

## 2. Fechamento

Ao realizar o fechamento, a escala daquele período passa a ser considerada fechada.

A escala fechada deve permanecer disponível para consulta.

O fechamento deve preservar:

* a escala materializada;
* o período correspondente;
* o estado de fechamento;
* o histórico necessário para rastreabilidade.

O fechamento representa o encerramento do ciclo normal de alterações da escala.

---

## 3. Escala fechada

Depois do fechamento:

* a consulta da escala permanece disponível;
* alterações livres não são permitidas;
* alterações posteriores dependem de autorização da Divisão de Enfermagem.

O sistema deve impedir alterações que não estejam autorizadas conforme as regras de permissão e fechamento.

O fechamento não deve impedir a consulta histórica da escala.

---

## 4. Alterações posteriores ao fechamento

Quando houver necessidade de alteração em uma escala fechada, a alteração deve ocorrer por meio de um processo autorizado.

A alteração posterior não deve apagar o estado anteriormente fechado.

O sistema deve preservar a distinção entre:

* escala materializada originalmente;
* escala fechada;
* alteração autorizada;
* resultado posterior à alteração.

A alteração posterior não deve fazer parecer que o novo estado sempre foi o estado originalmente materializado.

---

## 5. Reabertura

A Divisão de Enfermagem pode autorizar a liberação de uma escala fechada para alteração.

A reabertura deve ser tratada como uma ação excepcional e rastreável.

A reabertura não deve apagar o registro de que a escala havia sido fechada.

Quando uma escala for reaberta, o sistema deve preservar:

* o fechamento anterior;
* a identificação da reabertura;
* o responsável pela autorização;
* a data e hora da ação;
* as alterações realizadas posteriormente.

---

## 6. Materialização e fechamento

A materialização representa a decisão definida para o período.

O fechamento representa o encerramento do ciclo normal de alterações daquela escala.

São conceitos distintos:

**Materialização → decisão consolidada para o período.**

**Fechamento → encerramento do ciclo normal de alterações.**

Uma escala pode estar materializada antes de ser fechada.

O fechamento não substitui a materialização nem cria uma nova escala.

---

## 7. Fonte da verdade

A escala materializada é a fonte da verdade da decisão definida para aquele período.

O fechamento não substitui essa fonte de verdade.

Uma alteração posterior autorizada deve preservar o estado materializado anteriormente, permitindo identificar o que havia sido definido originalmente.

A escala fechada continua sendo consultável mesmo quando posteriormente houver alteração autorizada.

---

## 8. Auditoria

Alterações realizadas após o fechamento devem ser rastreáveis.

O histórico deve permitir identificar, conforme a natureza da operação:

* o estado anterior;
* o estado posterior;
* o período afetado;
* a alteração realizada;
* quem realizou a alteração;
* quem autorizou a alteração, quando houver autorização distinta;
* data e hora da operação;
* motivo da alteração, quando exigido pelo processo.

A auditoria deve permitir identificar que a alteração ocorreu depois do fechamento.

---

## 9. Histórico

O histórico de uma escala fechada não deve ser apagado ou substituído silenciosamente.

Quando uma alteração posterior ocorrer, o sistema deve preservar a relação entre o estado anterior e o novo estado.

O histórico deve permitir reconstruir a sequência relevante de decisões.

A existência de uma alteração posterior não invalida o registro histórico da escala que havia sido materializada e fechada anteriormente.

---

## 10. Permissões

A Divisão de Enfermagem possui responsabilidade sobre alterações posteriores ao fechamento, conforme definido em `03-permissoes-e-papeis.md`.

Nenhum outro perfil deve receber automaticamente permissão para alterar escalas fechadas apenas por possuir acesso à escala.

As permissões específicas para:

* fechar;
* autorizar reabertura;
* realizar alteração após fechamento;
* consultar histórico;

devem respeitar as regras de papéis e escopo.

---

## 11. Princípio contra alteração silenciosa

Não deve existir alteração silenciosa de uma escala fechada.

Toda alteração posterior ao fechamento deve possuir registro suficiente para identificar que:

1. a escala já estava fechada;
2. houve uma ação posterior;
3. a ação foi autorizada conforme as regras aplicáveis;
4. o estado anterior foi preservado;
5. o novo estado foi registrado.

---

## 12. Automação

A automação não deve reabrir, alterar ou substituir automaticamente uma escala fechada.

Uma inconsistência identificada após o fechamento pode ser apresentada como alerta ou pendência.

A decisão sobre eventual alteração deve ser tomada por usuário autorizado.

---

## 13. Regra para agentes

O agente de desenvolvimento deve tratar fechamento e auditoria como mecanismos de proteção do histórico da escala.

O agente não deve:

* alterar silenciosamente uma escala fechada;
* apagar o estado anterior;
* considerar reabertura como simples mudança de status sem histórico;
* permitir alterações após fechamento sem autorização;
* substituir o histórico por apenas o estado mais recente;
* inventar permissões de reabertura;
* alterar automaticamente uma escala fechada para resolver conflitos ou problemas de cobertura.

Quando uma regra de autorização ou auditoria não estiver definida, o agente deve identificar a pendência em vez de criar uma regra própria.

---

## 14. Relação com outros documentos

As regras deste documento devem ser consideradas em conjunto com:

* `02-regras-de-negocio.md` — regras transversais;
* `03-permissoes-e-papeis.md` — papéis, permissões e escopo;
* `04-cadastros-e-lotacoes.md` — servidores e lotações;
* `05-escalas-e-plantoes.md` — escalas, materialização e jornadas;
* `07-intercorrencias-e-compensacoes.md` — ocorrências e alterações decorrentes;
* `08-dimensionamento.md` — cobertura e análise da escala;
* `10-relatorios.md` — consulta e apresentação do histórico.

---

## 15. Princípio final

O Escalar deve preservar a história da escala.

Uma decisão materializada e posteriormente fechada não deve desaparecer porque houve uma alteração posterior.

O sistema deve permitir identificar claramente:

**o que foi planejado → o que foi materializado → o que foi fechado → o que foi alterado posteriormente → qual é o estado atual.**
