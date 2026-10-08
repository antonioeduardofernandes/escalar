# Escalar — Relatórios

## 1. Objetivo

O Escalar deve permitir a consulta e geração de relatórios relacionados às escalas e aos registros diretamente associados a elas.

Os relatórios devem apresentar informações derivadas dos dados registrados no sistema.

---

## 2. Princípio

O relatório deve derivar da escala e das informações diretamente relacionadas a ela.

O relatório não deve inventar, estimar ou alterar informações que não estejam presentes nos registros utilizados como fonte.

Quando uma informação for calculada, o cálculo deve possuir regra definida no sistema.

---

## 3. Fontes dos relatórios

Os relatórios podem utilizar como fonte:

* escala planejada;
* escala materializada;
* escala realizada;
* registros de intercorrências;
* faltas;
* licenças;
* férias;
* compensações;
* servidores;
* lotações;
* jornadas;
* dimensionamento;
* demais informações diretamente relacionadas à escala.

A fonte utilizada deve ser compatível com o objetivo do relatório.

---

## 4. Escala como fonte de informação

Quando o relatório tiver como objetivo representar a escala definida para determinado período, a escala materializada deve ser utilizada como referência.

O relatório não deve substituir a escala materializada por informações posteriores sem que exista regra explícita para isso.

Quando o relatório tiver como objetivo representar a realização, ocorrências ou alterações posteriores, essas informações devem ser apresentadas de forma distinta da escala originalmente materializada.

---

## 5. Faltas

As faltas devem ser registradas no sistema quando ocorrerem ou forem registradas.

Os relatórios correspondentes devem considerar as faltas registradas no período.

O registro da falta não deve apagar a informação da escala que estava materializada.

Quando aplicável, o relatório deve permitir distinguir:

* jornada prevista/materializada;
* falta registrada;
* realização efetiva;
* eventual compensação.

---

## 6. Intercorrências

Os relatórios devem considerar os registros de intercorrências relacionados ao período consultado.

Quando uma intercorrência possuir períodos distintos, esses períodos devem permanecer identificáveis no relatório.

O relatório não deve mesclar artificialmente períodos distintos apenas para simplificar a apresentação.

---

## 7. Compensações

Os relatórios devem permitir apresentar as compensações registradas e, quando aplicável, sua relação com a ocorrência que as originou.

A compensação não deve substituir ou apagar a ocorrência original no relatório histórico.

Quando relevante, deve ser possível identificar:

* ocorrência de origem;
* servidor;
* período;
* compensação;
* situação correspondente.

---

## 8. Relatórios mensais

O sistema deve permitir a geração de relatórios referentes ao período mensal da escala.

Os relatórios podem consolidar informações do período, conforme o objetivo de cada relatório.

A consolidação não deve eliminar informações necessárias para compreender a origem dos dados apresentados.

---

## 9. Consistência

O relatório deve refletir o estado consolidado dos dados utilizados como fonte.

Não deve apresentar informação diferente da escala materializada sem que exista uma regra explícita que justifique a diferença.

Quando houver alteração autorizada após o fechamento, o relatório deve respeitar as regras de histórico e permitir distinguir, quando necessário:

* estado originalmente materializado;
* alteração posterior;
* estado atual.

---

## 10. Histórico

Os relatórios históricos devem respeitar os registros preservados pelo sistema.

Uma alteração posterior não deve apagar a informação de que existia uma escala materializada ou fechada anteriormente.

Quando necessário para auditoria, o relatório deve permitir identificar a sequência entre:

**planejamento → materialização → fechamento → alteração posterior.**

---

## 11. Filtros e consulta

Os relatórios devem permitir filtros compatíveis com a finalidade de cada relatório.

Entre os possíveis critérios estão:

* período;
* servidor;
* matrícula;
* setor;
* lotação;
* jornada;
* regime;
* situação;
* ocorrência;
* compensação.

Os filtros efetivamente disponíveis em cada relatório devem ser definidos conforme sua finalidade.

O sistema não deve criar filtros sem necessidade funcional.

---

## 12. Formatos

O sistema deve contemplar geração de relatórios nos seguintes formatos:

* PDF;
* Excel.

A geração em diferentes formatos deve preservar os mesmos dados e critérios utilizados no relatório correspondente.

A diferença entre formatos deve estar principalmente na apresentação e adequação ao uso de cada formato, e não no conteúdo dos dados.

---

## 13. Dados calculados

Quando um relatório apresentar valores calculados, como:

* quantidade de plantões;
* horas;
* carga horária;
* cobertura;
* faltas;
* compensações;

o cálculo deve utilizar regras previamente definidas pelo sistema.

O relatório não deve criar uma regra própria de cálculo apenas para produzir determinado número.

Quando o significado de um cálculo não estiver definido, a regra deve ser estabelecida antes da implementação.

---

## 14. Rastreabilidade

Quando necessário, o relatório deve permitir identificar a origem das informações apresentadas.

Informações relevantes devem poder ser relacionadas aos registros que as originaram, especialmente em situações envolvendo:

* alterações posteriores;
* ocorrências;
* compensações;
* fechamento;
* auditoria.

---

## 15. Automação

A geração de relatórios pode ser automatizada.

A automação deve apenas consultar, consolidar e apresentar os dados segundo as regras definidas.

A geração de um relatório não deve alterar os dados utilizados como fonte.

---

## 16. Regra para agentes

O agente de desenvolvimento deve tratar relatórios como uma representação dos dados existentes no sistema.

O agente não deve:

* inventar informações;
* alterar dados para produzir um relatório;
* criar cálculos sem regra definida;
* substituir a escala materializada por dados posteriores sem regra explícita;
* ocultar alterações posteriores relevantes;
* tratar PDF e Excel como fontes de dados diferentes;
* criar filtros ou relatórios sem definição funcional.

Quando um relatório exigir uma informação ou cálculo cuja regra não esteja definida, a situação deve ser identificada como pendência de negócio.

---

## 17. Relação com outros documentos

As regras deste documento devem ser consideradas em conjunto com:

* `02-regras-de-negocio.md` — regras transversais;
* `04-cadastros-e-lotacoes.md` — servidores e lotações;
* `05-escalas-e-plantoes.md` — escalas e jornadas;
* `07-intercorrencias-e-compensacoes.md` — ocorrências e compensações;
* `08-dimensionamento.md` — cobertura e dimensionamento;
* `09-fechamento-e-auditoria.md` — fechamento e histórico.

Os relatórios devem respeitar as regras definidas nesses documentos.
