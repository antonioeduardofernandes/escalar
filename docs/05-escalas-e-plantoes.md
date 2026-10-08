# Escalar — Escalas e Plantões

## 1. Escala mensal

A escala do Escalar é organizada por período mensal.

O ciclo da escala compreende:

1. planejamento;
2. ajustes e revisão;
3. pré-visualização;
4. confirmação/materialização;
5. fechamento;
6. eventuais alterações posteriores autorizadas.

O fluxo pode possuir estados intermediários necessários à operação, mas a escala deve preservar a distinção entre aquilo que está sendo planejado, aquilo que foi materializado e aquilo que efetivamente foi realizado.

---

## 2. Planejamento

Durante o planejamento, o responsável pela escala pode construir e ajustar as alocações dentro das permissões e regras aplicáveis.

O planejamento pode utilizar:

* servidores;
* lotações;
* regimes;
* jornadas;
* equipes;
* modelos;
* regras de cobertura;
* outras informações necessárias à construção da escala.

Alterações realizadas durante o planejamento não devem ser tratadas como alterações de uma escala já materializada.

---

## 3. Pré-visualização

A pré-visualização permite consultar o resultado planejado antes da confirmação/materialização.

A pré-visualização pode apresentar:

* servidores;
* dias;
* jornadas;
* cobertura;
* conflitos;
* alertas;
* outras informações relevantes para a revisão.

A pré-visualização não representa, por si só, a materialização definitiva da escala.

---

## 4. Materialização

A materialização representa a confirmação da escala definida para o período.

A escala materializada é a fonte da verdade para aquilo que foi definido para aquele período.

A materialização deve preservar o resultado confirmado pelo responsável pela escala.

Alterações posteriores não devem apagar ou reescrever silenciosamente a materialização anterior.

A materialização não deve ser confundida com a realização efetiva dos plantões.

---

## 5. Realização

O que foi materializado representa o que foi definido para o período.

A realização representa o que efetivamente ocorreu.

Faltas, licenças, intercorrências, compensações e outras ocorrências posteriores podem fazer com que a realização seja diferente da escala materializada.

Essas situações devem ser registradas sem apagar a informação originalmente materializada.

---

## 6. Jornadas principais

O Escalar possui as seguintes jornadas principais.

### 6.1 SD

**SD — 07:00 às 19:00**

Jornada de 12 horas no período diurno.

### 6.2 SN

**SN — 19:00 às 07:00**

Jornada de 12 horas no período noturno, atravessando para o dia seguinte.

### 6.3 DN

**DN — 07:00 às 07:00 do dia seguinte**

Jornada de 24 horas.

Para fins de contagem de jornada/carga horária, DN corresponde a duas jornadas de 12 horas.

DN deve permanecer como uma jornada de 24 horas para fins de registro da escala, não devendo ser automaticamente transformado em dois lançamentos independentes apenas para representação visual.

### 6.4 M

**M — 07:00 às 13:00**

Jornada de 6 horas no período da manhã.

### 6.5 T

**T — 13:00 às 19:00**

Jornada de 6 horas no período da tarde.

### 6.6 MT

**MT — jornada configurável**

A jornada MT possui horário de entrada e saída configuráveis.

A duração prevista pode ser de:

* 8 horas; ou
* 10 horas.

A configuração deve determinar explicitamente os horários de entrada e saída.

---

## 7. Jornadas especiais

Podem existir jornadas especiais diferentes das jornadas padronizadas quando houver autorização da autoridade responsável conforme as regras do sistema.

Uma jornada especial não deve ser criada automaticamente apenas para contornar uma validação ou conflito.

A jornada especial deve possuir horário de entrada e saída definidos.

Sua utilização deve ser identificável na escala.

As regras específicas de autorização e utilização de jornadas especiais devem ser definidas antes da implementação da funcionalidade.

---

## 8. Intervalo mínimo entre jornadas

Deve ser respeitado intervalo mínimo de **12 horas** entre jornadas, conforme as regras aplicáveis ao servidor e à combinação das jornadas.

O sistema deve identificar combinações que resultem em intervalo inferior ao permitido.

Uma combinação que viole o intervalo mínimo deve ser impedida quando a regra for aplicável.

A validação deve considerar o horário real de término da jornada e o horário de início da jornada seguinte, inclusive quando a jornada atravessar a meia-noite.

---

## 9. Jornadas de 36 horas

Jornadas de 36 horas são proibidas.

O sistema deve impedir uma alocação que resulte em jornada de 36 horas conforme as regras de composição de jornadas.

A existência de jornadas consecutivas não deve ser interpretada automaticamente como jornada de 36 horas sem que a combinação efetivamente produza essa situação.

---

## 10. Conflitos de jornada

O sistema deve identificar e impedir combinações de jornadas incompatíveis.

Entre os conflitos conhecidos estão:

* sobreposição de horários;
* intervalo inferior a 12 horas;
* composição que resulte em jornada de 36 horas;
* outras incompatibilidades definidas pelas regras de jornada.

Quando uma situação não possuir regra definida, o sistema não deve inventar uma restrição.

A regra deve ser definida antes de ser transformada em validação obrigatória.

---

## 11. Lançamentos no mesmo dia

A existência de mais de uma jornada no mesmo dia não deve ser considerada automaticamente um erro.

A possibilidade de múltiplas jornadas no mesmo dia depende da combinação das jornadas e das demais regras aplicáveis.

O sistema deve validar a combinação efetiva de horários, duração e intervalo, em vez de simplesmente bloquear qualquer segundo lançamento na mesma data.

As combinações permitidas e proibidas devem ser detalhadas conforme as regras de jornada estabelecidas.

---

## 12. Regime

O servidor possui um regime cadastrado:

* diarista; ou
* plantonista.

O regime deve ser considerado na construção e validação da escala.

A alteração de regime não deve criar um novo servidor.

A alteração de regime não deve reescrever retroativamente plantões já materializados.

A vigência da alteração deve ser respeitada para as escalas afetadas posteriormente.

As regras específicas de alteração e vigência do regime são definidas em `04-cadastros-e-lotacoes.md`.

---

## 13. Lotação e alocação

A alocação do servidor deve respeitar sua lotação e as regras aplicáveis ao setor.

Atuações excepcionais em outro setor devem ser tratadas conforme as regras de APH quando se enquadrarem nessa situação.

A alocação não deve alterar automaticamente a lotação principal do servidor.

---

## 14. Servidor inativo

Servidor inativo não pode receber novas alocações.

A inativação não deve apagar registros históricos nem escalas já materializadas.

O comportamento específico de plantões futuros já existentes no momento da inativação deve respeitar as regras de vigência e de execução da escala.

A simples alteração do cadastro para inativo não deve apagar silenciosamente uma decisão anteriormente materializada.

---

## 15. Alterações após a materialização

A materialização não impede toda e qualquer alteração posterior.

Alterações posteriores devem respeitar o estado da escala, as permissões do usuário e as regras de fechamento.

Quando uma alteração posterior for autorizada, o sistema deve preservar a informação sobre o que havia sido materializado anteriormente.

A alteração posterior não deve fazer parecer que a nova situação sempre foi a decisão original.

---

## 16. Fechamento

O fechamento representa o encerramento do ciclo operacional da escala para aquele período.

Após o fechamento, a escala não deve ser alterada livremente.

Alterações posteriores dependem de autorização conforme as regras de permissões e fechamento.

A necessidade de alteração posterior não deve apagar o registro do fechamento nem a materialização anterior.

As regras detalhadas de fechamento e alterações posteriores devem ser definidas em `09-fechamento-e-auditoria.md`.

---

## 17. Histórico da escala

O sistema deve preservar o histórico das mudanças relevantes realizadas na escala.

Quando uma escala materializada sofrer alteração autorizada, deve ser possível distinguir:

* o que havia sido materializado;
* qual alteração foi realizada;
* quando a alteração ocorreu;
* quem realizou ou autorizou a alteração, conforme as regras de auditoria.

A edição de uma escala não deve destruir silenciosamente o estado anterior quando esse estado for necessário para rastreabilidade.

---

## 18. Automação

O sistema pode auxiliar na construção da escala por meio de:

* sugestões de alocação;
* identificação de conflitos;
* validação de jornadas;
* identificação de insuficiência de cobertura;
* aplicação de modelos;
* outras formas de apoio à decisão.

A automação não deve substituir a decisão do gestor.

Uma sugestão automática somente se torna parte da escala quando for aceita e materializada conforme o fluxo definido.

O sistema não deve alterar automaticamente uma escala materializada para resolver um conflito posterior.

---

## 19. Regra para agentes

O agente de desenvolvimento deve implementar somente as regras de jornada e escala que estejam documentadas.

O agente não deve:

* criar novos tipos de jornada sem aprovação;
* alterar horários das jornadas existentes sem aprovação;
* criar jornadas especiais automaticamente;
* considerar toda segunda jornada no mesmo dia como inválida sem regra que determine isso;
* alterar uma escala materializada para resolver automaticamente um conflito;
* transformar uma jornada de 24 horas em dois lançamentos visuais sem que isso seja definido como comportamento da interface;
* inventar regras para situações não especificadas.

Quando houver uma combinação de jornadas cuja validade não esteja definida, a situação deve ser identificada como pendência de negócio.

---

## 20. Relação com outros documentos

Este documento define as regras de escalas e plantões.

As regras relacionadas devem ser consultadas em conjunto com:

* `02-regras-de-negocio.md` — regras transversais;
* `03-permissoes-e-papeis.md` — permissões para operação da escala;
* `04-cadastros-e-lotacoes.md` — servidores, regimes e lotações;
* `06-equipes-e-modelos.md` — equipes e modelos utilizados na construção;
* `07-intercorrencias-e-compensacoes.md` — ocorrências posteriores e compensações;
* `08-dimensionamento.md` — cobertura e dimensionamento;
* `09-fechamento-e-auditoria.md` — fechamento e alterações posteriores.

Quando houver necessidade de uma regra ainda não definida, ela deve ser decidida e documentada antes da implementação.
