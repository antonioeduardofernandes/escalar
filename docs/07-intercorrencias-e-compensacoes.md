# Escalar — Intercorrências e Compensações

## 1. Objetivo

O Escalar deve permitir registrar ocorrências que afetem o planejamento, a execução ou a compensação de jornadas dos servidores.

O registro de uma ocorrência deve preservar a informação do que aconteceu sem apagar ou reescrever silenciosamente a escala que havia sido planejada ou materializada.

---

## 2. Intercorrências

Intercorrências possuem, no mínimo:

* código;
* período.

O código identifica o tipo ou a classificação da intercorrência conforme os cadastros e regras do sistema.

O período identifica quando a intercorrência ocorreu ou esteve vigente.

As informações da intercorrência devem ser registradas de forma estruturada.

---

## 3. Períodos das intercorrências

Uma intercorrência deve preservar seus períodos individualmente.

Períodos distintos não devem ser mesclados artificialmente em um único registro apenas porque pertencem à mesma intercorrência.

Quando uma mesma intercorrência possuir períodos separados, cada período deve permanecer identificável.

Exemplo:

* período 1: determinado intervalo de datas;
* período 2: outro intervalo de datas.

O sistema não deve transformar automaticamente esses dois períodos em um único período contínuo.

---

## 4. Faltas

Faltas devem ser registradas no sistema.

O registro da falta deve preservar:

* o servidor relacionado;
* o período correspondente;
* a informação necessária para identificar a ocorrência;
* o histórico da ocorrência.

A falta deve aparecer nos relatórios correspondentes ao período.

O registro de uma falta não deve apagar a escala materializada que existia anteriormente.

Quando a falta ocorrer sobre um plantão já materializado, deve ser possível distinguir:

* o que estava previsto na escala;
* a ocorrência registrada;
* o que efetivamente ocorreu.

---

## 5. Licenças

Licenças devem ser registradas no sistema com seu período de vigência.

Licenças devem ser consideradas no planejamento das escalas afetadas pelo período correspondente.

O registro da licença não deve destruir a escala ou o histórico anteriormente existente.

Quando a licença afetar uma escala já materializada, a ocorrência deve ser registrada sem apagar a informação originalmente materializada.

Os efeitos da licença sobre a realização e eventuais compensações devem ser tratados conforme as regras aplicáveis.

---

## 6. Férias

Férias devem ser registradas no sistema com seu período correspondente.

As férias devem ser consideradas durante o planejamento das escalas.

O planejamento não deve ser destruído pelo registro das férias.

Quando as férias forem registradas após uma escala já ter sido materializada, o registro da ocorrência não deve apagar silenciosamente a materialização anterior.

Deve ser possível distinguir a escala originalmente definida da ocorrência posteriormente registrada.

---

## 7. Efeito das ocorrências no planejamento

Ocorrências conhecidas antes da materialização devem ser consideradas durante o planejamento da escala.

O sistema pode utilizar essas informações para:

* alertar sobre indisponibilidade;
* identificar conflitos;
* auxiliar o responsável pela escala;
* evitar novas alocações incompatíveis;
* apoiar a identificação de necessidade de cobertura ou compensação.

A ocorrência não deve alterar automaticamente a escala sem que essa alteração esteja prevista pelas regras do sistema e seja realizada conforme as permissões aplicáveis.

---

## 8. Ocorrências após a materialização

Uma ocorrência pode ser registrada depois que a escala tenha sido materializada.

Nesse caso, o registro da ocorrência não deve apagar ou reescrever a escala materializada.

A ocorrência representa um fato ou situação posterior à decisão registrada na escala.

Quando houver necessidade de alterar a escala em consequência da ocorrência, a alteração deve seguir as regras de alteração da escala e de fechamento.

Deve ser possível identificar a relação entre:

* escala materializada;
* ocorrência;
* eventual alteração posterior;
* eventual compensação.

---

## 9. Compensações

Compensações devem ser registradas quando forem aplicáveis.

Uma compensação deve preservar a relação com a ocorrência que a originou.

O registro da compensação deve permitir identificar, no mínimo:

* a ocorrência de origem;
* o servidor relacionado;
* a compensação correspondente;
* o período ou jornada compensatória, quando aplicável;
* o histórico da relação.

A compensação não deve apagar a ocorrência original.

---

## 10. Relação entre ocorrência e compensação

A compensação deve ser tratada como consequência ou tratamento da ocorrência, e não como substituição do registro original.

Exemplo conceitual:

> uma ocorrência gera uma necessidade de compensação → a compensação é registrada vinculada à ocorrência → a ocorrência original permanece preservada.

A compensação não deve alterar retroativamente o fato que originou sua necessidade.

---

## 11. Histórico

Ocorrências e compensações devem preservar rastreabilidade.

Alterações relevantes devem manter histórico suficiente para identificar:

* situação anterior;
* situação posterior;
* período afetado;
* responsável pela alteração, quando aplicável;
* relação com outros registros envolvidos.

O sistema não deve apagar uma ocorrência apenas porque ela posteriormente foi corrigida ou compensada.

Quando houver correção, o histórico deve permitir identificar a alteração realizada.

---

## 12. Relação com a escala materializada

A escala materializada representa a decisão definida para o período.

Ocorrências posteriores não devem transformar silenciosamente a escala materializada em outro registro histórico.

O sistema deve preservar a distinção entre:

**Escala materializada → o que foi definido.**

**Ocorrência → o que aconteceu ou foi registrado posteriormente.**

**Realização → o que efetivamente ocorreu.**

**Compensação → tratamento decorrente de uma ocorrência, quando aplicável.**

Essa distinção deve ser preservada mesmo quando os registros estiverem relacionados.

---

## 13. Relatórios

As ocorrências devem estar disponíveis nos relatórios correspondentes aos períodos afetados.

Os relatórios devem permitir, quando aplicável, relacionar:

* servidor;
* escala;
* período;
* ocorrência;
* compensação;
* situação da ocorrência.

O registro de uma ocorrência não deve fazer desaparecer a informação da escala originalmente materializada dos relatórios históricos.

---

## 14. Automação

O sistema pode utilizar ocorrências para apoiar:

* planejamento;
* identificação de conflitos;
* identificação de indisponibilidade;
* identificação de necessidade de cobertura;
* identificação de possíveis compensações;
* geração de alertas.

A automação não deve alterar silenciosamente uma escala materializada para resolver os efeitos de uma ocorrência.

Quando uma decisão operacional for necessária, ela deve ser tomada pelo responsável autorizado.

---

## 15. Regra para agentes

O agente de desenvolvimento deve implementar ocorrências e compensações como registros relacionados e rastreáveis.

O agente não deve:

* apagar uma escala materializada por causa de uma ocorrência;
* mesclar automaticamente períodos distintos;
* transformar uma ocorrência em compensação sem decisão aplicável;
* apagar a ocorrência original quando houver compensação;
* inventar tipos de ocorrência;
* inventar regras de compensação;
* alterar retroativamente a história da escala.

Quando a regra para determinada ocorrência ou compensação não estiver definida, a situação deve ser tratada como pendência de negócio.

---

## 16. Relação com outros documentos

As regras deste documento devem ser consideradas em conjunto com:

* `02-regras-de-negocio.md` — regras transversais;
* `04-cadastros-e-lotacoes.md` — servidores e lotações;
* `05-escalas-e-plantoes.md` — escalas, materialização e realização;
* `08-dimensionamento.md` — cobertura;
* `09-fechamento-e-auditoria.md` — alterações posteriores e rastreabilidade;
* `10-relatorios.md` — apresentação das ocorrências e compensações.

Regras específicas de tipos de ocorrência e critérios de compensação devem ser definidas antes da implementação dessas funcionalidades.
