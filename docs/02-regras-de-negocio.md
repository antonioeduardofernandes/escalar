# Escalar — Regras de Negócio

## 1. Regra central

> **Automação propõe. O gestor decide. A escala materializada é a fonte da verdade.**

Nenhum algoritmo de geração automática pode substituir uma decisão explícita do responsável pela escala.

O sistema pode sugerir alocações, identificar conflitos, validar regras e apontar insuficiências, mas não deve alterar silenciosamente uma decisão já tomada pelo gestor.

---

## 2. Escopo deste documento

Este documento consolida as regras de negócio centrais e transversais do Escalar.

As regras específicas de cada domínio devem ser detalhadas nos documentos correspondentes, evitando duplicação ou interpretações divergentes.

Quando houver conflito entre uma regra geral deste documento e uma regra específica posteriormente aprovada para determinado domínio, a inconsistência deve ser identificada e resolvida antes da implementação.

Uma decisão de negócio que ainda não tenha sido definida não deve ser inventada para completar a implementação.

---

## 3. Servidor

A matrícula é a identificação única do servidor no Escalar.

Deve existir apenas um cadastro de servidor para cada matrícula.

São dados de identificação do servidor:

* matrícula;
* nome;
* CPF;
* e-mail;
* ativo;
* data de nascimento, opcional.

Não existe nome social no cadastro do Escalar.

A estrutura detalhada do cadastro de servidores deve ser definida em `04-cadastros-e-lotacoes.md`.

---

## 4. Identidade e continuidade do cadastro

A matrícula identifica unicamente o servidor dentro do sistema.

Uma nova matrícula representa um novo registro de servidor.

Alterações cadastrais permitidas devem atualizar os dados correspondentes sem criar um novo servidor quando a identidade do registro continuar sendo a mesma.

As regras específicas de imutabilidade e alteração dos dados funcionais devem ser respeitadas conforme definido para o cadastro.

Dentro do mesmo cadastro:

* matrícula é imutável;
* cargo é imutável;
* vínculo é imutável;
* regime pode ser alterado sem alterar a matrícula, o cargo ou o vínculo.

Correções cadastrais permitidas não devem criar registros duplicados para o mesmo servidor.

---

## 5. Lotação

A lotação representa a vinculação operacional do servidor a uma unidade/setor.

A lotação possui histórico.

Alterações de lotação devem preservar o histórico anterior e não devem apagar a informação de onde o servidor esteve anteriormente lotado.

A alteração da lotação é controlada pela Divisão de Enfermagem.

A lotação deve ser considerada nas regras de alocação e validação da escala.

Uma alocação incompatível com as regras de lotação deve ser identificada e impedida quando a regra aplicável estiver definida.

As regras detalhadas de cadastro, alteração e vigência das lotações devem ser definidas em `04-cadastros-e-lotacoes.md`.

---

## 6. Escala

A escala é organizada por período mensal.

Cada escala possui um ciclo que contempla, conforme aplicável:

1. planejamento;
2. revisão e ajustes;
3. confirmação/materialização;
4. fechamento;
5. eventuais alterações posteriores autorizadas.

A escala materializada representa a decisão definida para aquele período.

A materialização não deve ser confundida com a realização efetiva dos plantões.

O que foi materializado deve permanecer preservado mesmo quando ocorrências posteriores alterarem o que efetivamente aconteceu.

---

## 7. Planejada, materializada e realizada

O Escalar deve distinguir:

* **planejada:** aquilo que está sendo construído durante o planejamento;
* **materializada:** aquilo que foi confirmado e passou a representar a escala definida para o período;
* **realizada:** aquilo que efetivamente ocorreu na execução.

Esses estados não devem ser tratados como equivalentes.

Uma alteração posterior na execução não deve apagar ou reescrever silenciosamente a informação anteriormente planejada ou materializada.

Ocorrências posteriores devem ser registradas de forma que seja possível compreender a diferença entre o que foi planejado, o que foi materializado e o que efetivamente ocorreu.

---

## 8. Jornadas e plantões

Os plantões devem obedecer às regras de jornada estabelecidas pelo Escalar.

Entre as regras gerais:

* deve ser respeitado o intervalo mínimo de 12 horas entre jornadas, conforme as regras aplicáveis;
* jornadas de 36 horas são proibidas;
* combinações incompatíveis de jornadas devem ser identificadas e impedidas;
* jornadas especiais somente podem existir quando autorizadas conforme as regras definidas para o sistema.

Os tipos de jornada, horários, equivalências e regras detalhadas de combinação devem ser definidos em `05-escalas-e-plantoes.md`.

O documento específico de escalas e plantões é a referência para o detalhamento operacional dessas regras.

---

## 9. Carga horária

A referência ordinária de planejamento é de **120 horas mensais**.

As 120 horas não constituem um limite universal aplicável indistintamente a todos os servidores e situações.

A apuração da carga deve considerar as regras específicas do regime, das jornadas e das situações excepcionais previstas no sistema.

APH deve ser tratado separadamente da carga horária ordinária.

As regras detalhadas de cálculo e apuração devem ser definidas nos documentos específicos de escalas, jornadas e APH.

---

## 10. APH

APH representa trabalho excepcional realizado em outro setor.

APH é separado da lotação principal do servidor.

APH não altera, por si só, a lotação principal do servidor.

APH não compõe a carga horária ordinária para os fins definidos nas regras do Escalar.

As regras detalhadas de lançamento, período, autorização e apuração de APH devem ser definidas no documento correspondente.

---

## 11. Alteração de regime

A alteração do regime do servidor não deve modificar retroativamente plantões já materializados.

A alteração deve respeitar sua vigência aplicável ao cadastro.

Escalas e registros anteriores à vigência da alteração devem permanecer preservados.

Uma alteração de regime não deve reescrever automaticamente escalas já materializadas.

As regras detalhadas de vigência devem ser definidas em `04-cadastros-e-lotacoes.md`.

---

## 12. Equipes e modelos

Equipes e modelos podem ser utilizados para facilitar a construção das escalas.

A aplicação de uma equipe ou modelo deve respeitar a vigência definida para sua utilização.

Uma alteração posterior em equipe ou modelo não deve reescrever automaticamente meses anteriores já materializados.

A escala materializada prevalece sobre o modelo utilizado para sua construção.

As regras detalhadas de equipes e modelos devem ser definidas em `06-equipes-e-modelos.md`.

---

## 13. Intercorrências

Intercorrências podem representar situações ocorridas durante determinado período.

Uma intercorrência deve possuir:

* código;
* período.

Períodos distintos devem permanecer identificáveis individualmente.

Períodos distintos não devem ser artificialmente mesclados em um único dia quando isso eliminar a informação sobre sua duração ou ocorrência.

As regras detalhadas de tipos, códigos, períodos e efeitos das intercorrências devem ser definidas em `07-intercorrencias-e-compensacoes.md`.

---

## 14. Faltas, licenças e outras ocorrências

Faltas, licenças, férias e demais ocorrências aplicáveis devem ser registradas no sistema quando fizerem parte do processo de gestão da escala.

Essas ocorrências devem preservar seu histórico e permitir a identificação de seu período.

Quando uma ocorrência afetar uma escala já planejada ou materializada, o registro da ocorrência não deve apagar silenciosamente a decisão anterior.

Os efeitos de cada tipo de ocorrência sobre planejamento, materialização, execução, carga horária e compensação devem ser definidos em `07-intercorrencias-e-compensacoes.md`.

---

## 15. Compensações

Compensações devem preservar a informação sobre o planejamento original e registrar a ocorrência que deu origem à compensação.

A compensação não deve apagar o histórico da escala original.

As regras de quando uma compensação é aplicável, como ela é registrada e como afeta a apuração devem ser definidas em `07-intercorrencias-e-compensacoes.md`.

---

## 16. Fechamento

Uma escala fechada não deve ser alterada livremente.

Alterações posteriores ao fechamento dependem de autorização da Divisão de Enfermagem, conforme as permissões estabelecidas para o sistema.

Alterações posteriores devem preservar rastreabilidade.

O fechamento não deve apagar ou substituir o histórico anterior da escala.

As regras detalhadas de fechamento, autorização e auditoria devem ser definidas em `09-fechamento-e-auditoria.md`.

---

## 17. Consistência

O sistema deve impedir ou sinalizar situações incompatíveis com regras de negócio já definidas.

Entre os exemplos:

* duplicidade de matrícula;
* alocação incompatível com a lotação, quando a regra aplicável estiver definida;
* intervalo inferior ao permitido;
* jornada de 36 horas;
* nova alocação de servidor que não esteja ativo;
* combinações de jornadas incompatíveis;
* outras violações das regras de jornada, lotação, cobertura ou fechamento.

A validação não deve criar uma nova regra de negócio.

Quando uma situação puder possuir mais de uma interpretação válida, a regra deve ser definida antes de sua implementação.

---

## 18. Histórico e rastreabilidade

Alterações relevantes nos dados e na escala devem preservar histórico quando a natureza da informação exigir rastreabilidade.

O sistema não deve apagar silenciosamente decisões anteriormente materializadas.

Deve ser possível distinguir alterações cadastrais, alterações de escala, ocorrências e alterações posteriores ao fechamento conforme as regras específicas de cada domínio.

As regras detalhadas de auditoria devem ser definidas em `09-fechamento-e-auditoria.md`.

---

## 19. Automação e decisão do gestor

A automação do Escalar deve atuar como mecanismo de apoio à decisão.

O sistema pode:

* sugerir alocações;
* identificar conflitos;
* validar regras;
* apontar insuficiência de cobertura;
* auxiliar na construção da escala;
* identificar possíveis inconsistências.

O sistema não deve, sem autorização prevista nas regras, substituir a decisão do gestor ou alterar silenciosamente uma escala já definida.

Quando houver conflito entre uma sugestão automática e uma decisão explícita do gestor, a decisão do gestor deve prevalecer, desde que não viole uma regra que o sistema deva obrigatoriamente impedir.

---

## 20. Regra para agentes

Agentes utilizados no desenvolvimento do Escalar não devem criar regras de negócio ausentes da documentação.

Quando houver dúvida funcional, ambiguidade ou ausência de definição:

1. a questão deve ser identificada;
2. nenhuma interpretação deve ser transformada automaticamente em regra oficial;
3. a decisão deve ser tomada no processo de definição do produto;
4. somente depois a regra aprovada deve ser incorporada à documentação.

Decisões técnicas podem ser tomadas durante a implementação quando não alterarem o comportamento de negócio previamente definido.

---

## 21. Princípio de preservação da decisão

Uma regra fundamental do Escalar é:

> **Uma decisão materializada não deve ser silenciosamente reescrita por uma alteração posterior de cadastro, modelo, lotação, ocorrência ou configuração.**

Quando uma mudança posterior afetar a execução da escala, o sistema deve preservar a informação anterior e registrar a nova situação conforme as regras específicas do domínio.

A escala materializada permanece como registro da decisão tomada para aquele período.

---

## 22. Fonte da verdade

Este documento, juntamente com os demais documentos funcionais aprovados em `docs/`, constitui a fonte de verdade das regras de negócio do Escalar.

Este documento define princípios e regras transversais.

As regras detalhadas de cada domínio devem permanecer nos documentos específicos correspondentes.

Nenhuma implementação deve criar comportamento de negócio apenas por conveniência técnica.

Quando uma regra ainda não estiver definida, ela deve ser tratada como uma pendência de especificação até que seja decidida e documentada.
