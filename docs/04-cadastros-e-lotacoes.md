# Escalar — Cadastros e Lotações

## 1. Unidade e setor

O Escalar atende o hospital como um todo.

O hospital é composto por unidades e/ou setores que representam estruturas organizacionais do sistema.

Cada setor pode possuir sua própria escala.

Unidades e setores são entidades estruturadas do sistema e não devem ser tratados como texto livre quando representarem conceitos organizacionais.

As entidades de unidade/setor podem, conforme as permissões administrativas:

* ser criadas;
* ser editadas;
* ser desativadas.

A desativação de uma unidade ou setor não deve apagar seu histórico.

As regras detalhadas de estrutura organizacional devem ser definidas conforme a necessidade dos módulos que utilizam essas entidades.

---

## 2. Servidor

O servidor possui dados de identificação e dados funcionais.

### 2.1 Dados de identificação

São dados de identificação:

* matrícula;
* nome;
* CPF;
* e-mail;
* ativo;
* data de nascimento, opcional.

Não existe nome social no cadastro do Escalar.

### 2.2 Dados funcionais

São considerados dados funcionais:

* cargo;
* vínculo;
* regime;
* lotação.

Não existem no cadastro do Escalar:

* função;
* categoria profissional.

A estrutura desses dados deve ser mantida de forma organizada, evitando transformar conceitos diferentes em campos de texto sem estrutura.

---

## 3. Matrícula

A matrícula é a identificação única do servidor no Escalar.

Deve existir apenas um cadastro de servidor para cada matrícula.

Uma nova matrícula representa um novo registro de servidor.

Uma nova matrícula não deve criar uma segunda identificação para o mesmo cadastro anterior.

A matrícula não pode ser alterada dentro do mesmo cadastro.

---

## 4. Cargo

O cargo faz parte dos dados funcionais do servidor.

O cargo não deve ser tratado como texto livre quando existir como entidade estruturada do sistema.

O cargo é imutável dentro do mesmo cadastro de servidor, conforme definido nas regras de negócio.

Não existe o conceito de função no cadastro do servidor.

---

## 5. Vínculo

O vínculo representa a relação funcional do servidor com a instituição.

As opções atualmente definidas são:

* Ministério da Saúde;
* Fiotec;
* contrato temporário.

Para contrato temporário, deve ser registrada a identificação do certame correspondente, como, por exemplo:

* 6º certame;
* 7º certame;
* 8º certame.

A lista definitiva de vínculos deve ser confirmada antes da implementação caso existam outros vínculos institucionais a serem contemplados.

O vínculo é imutável dentro do mesmo cadastro de servidor, conforme definido nas regras de negócio.

---

## 6. Regime

O regime define a forma de organização da jornada do servidor.

As opções atualmente definidas são:

* diarista;
* plantonista.

O regime pode ser alterado sem criar um novo cadastro de servidor.

A alteração do regime deve preservar o histórico e não deve reescrever retroativamente escalas já materializadas.

As regras de vigência da alteração devem ser respeitadas.

---

## 7. Lotação

A lotação representa a vinculação do servidor a uma unidade/setor para fins de atuação no Escalar.

A lotação possui histórico.

Alterações de lotação não devem apagar a informação sobre lotações anteriores.

A alteração da lotação é controlada pela Divisão de Enfermagem.

A lotação deve possuir informação suficiente para identificar:

* o servidor;
* a unidade/setor;
* o período de vigência da lotação.

As regras detalhadas de vigência, transferência e histórico devem ser definidas antes da implementação desses comportamentos.

---

## 8. Relação entre lotação e escala

A lotação deve ser considerada nas regras de alocação e validação da escala.

Um servidor não deve ser alocado em desacordo com as regras aplicáveis à sua lotação.

Atuações excepcionais em outro setor são tratadas como APH quando se enquadrarem nas regras de APH.

APH não altera, por si só, a lotação principal do servidor.

As regras detalhadas de alocação, exceções e APH devem ser definidas em `05-escalas-e-plantoes.md` e `07-intercorrencias-e-compensacoes.md`, conforme o caso.

---

## 9. Inativação

O servidor possui uma situação de ativo/inativo.

A inativação impede novas operações que dependam de um servidor ativo, conforme as regras específicas de cada módulo.

Um servidor inativo não deve receber novas alocações.

A inativação não deve apagar o cadastro nem seu histórico.

Registros históricos e escalas já materializadas devem permanecer preservados.

O comportamento específico de plantões futuros existentes no momento da inativação deve ser definido nas regras de escalas e fechamento, não sendo automaticamente alterado ou apagado pela simples mudança de situação cadastral.

A reativação deve restabelecer a possibilidade de utilização do servidor nas operações permitidas, respeitando as regras de vigência e de escala.

---

## 10. Histórico

Alterações relevantes nos dados funcionais e de lotação devem preservar histórico quando sua alteração puder afetar a interpretação de registros anteriores.

O histórico deve permitir distinguir, conforme aplicável:

* situação anterior;
* situação posterior;
* período de vigência;
* responsável pela alteração.

A alteração de dados atuais não deve apagar informações necessárias para compreender registros históricos.

---

## 11. Relação com escalas materializadas

Alterações posteriores no cadastro do servidor, no regime ou na lotação não devem reescrever silenciosamente escalas já materializadas.

Quando uma alteração cadastral tiver efeito futuro, ela deve respeitar sua vigência.

A escala materializada permanece como registro da decisão tomada para o período correspondente.

Alterações posteriores devem ser tratadas conforme as regras de escala, fechamento e auditoria.

---

## 12. Regras para implementação

O cadastro deve representar os conceitos de servidor, cargo, vínculo, regime, unidade/setor e lotação de forma estruturada.

O agente não deve:

* criar novos campos funcionais não previstos;
* criar os conceitos de função ou categoria profissional;
* transformar conceitos estruturados em texto livre apenas por conveniência técnica;
* alterar retroativamente escalas materializadas em razão de uma alteração cadastral;
* inventar novos tipos de vínculo;
* criar regras de vigência não definidas;
* apagar histórico para simplificar a implementação.

Quando houver dúvida sobre a estrutura ou comportamento de um cadastro, a decisão deve ser definida antes da implementação.

---

## 13. Pendências de definição

Antes da implementação definitiva do cadastro e das lotações, devem ser confirmadas:

* se **Estado** fará parte das opções de vínculo;
* estrutura definitiva de unidades e setores;
* se unidade e setor possuem relação hierárquica obrigatória;
* regras completas de vigência da lotação;
* comportamento de transferências com relação a escalas futuras;
* comportamento de plantões futuros quando um servidor é inativado;
* regras para alteração de cargo ou vínculo, caso alguma situação excepcional exija revisão;
* regras de vigência para alteração de regime;
* necessidade de histórico detalhado de alterações cadastrais.

Essas pendências não devem ser resolvidas por suposição durante a implementação.
