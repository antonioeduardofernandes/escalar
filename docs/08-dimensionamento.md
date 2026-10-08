# Escalar — Dimensionamento e Cobertura

## 1. Objetivo

O Escalar deve permitir verificar se a escala atende às necessidades de cobertura dos setores.

O dimensionamento é um mecanismo de análise e apoio à decisão.

O dimensionamento não substitui a escala e não deve alterar automaticamente as alocações definidas pelo responsável.

---

## 2. Necessidade de cobertura

A análise de cobertura deve considerar a necessidade do setor para cada período relevante.

A necessidade pode estar relacionada a:

* setor;
* data;
* horário;
* jornada;
* quantidade de servidores necessária;
* outras características definidas para o dimensionamento.

A forma de cadastro e cálculo da necessidade de cobertura deve ser definida conforme as regras específicas de dimensionamento.

O sistema não deve inventar critérios de necessidade que ainda não tenham sido definidos.

---

## 3. Cobertura da escala

A cobertura deve comparar a necessidade identificada para o setor com os servidores e jornadas alocados na escala.

A análise deve permitir identificar, quando aplicável:

* cobertura suficiente;
* insuficiência de cobertura;
* excesso de servidores;
* conflito de cobertura;
* períodos sem cobertura;
* outras situações relevantes definidas nas regras de dimensionamento.

O resultado da análise deve ser apresentado de forma compreensível para o responsável pela escala.

---

## 4. Planejamento

Durante o planejamento, o dimensionamento pode ser utilizado para auxiliar a construção da escala.

O sistema pode identificar previamente:

* períodos sem cobertura suficiente;
* excesso de servidores;
* conflitos;
* necessidade de ajustes.

Essas informações devem servir como apoio à decisão do responsável.

O sistema não deve alterar automaticamente a escala para corrigir uma insuficiência ou excesso de cobertura.

---

## 5. Materialização

Após a materialização, a análise de cobertura deve considerar a escala materializada como referência da decisão definida para aquele período.

Uma insuficiência identificada não deve provocar alteração automática da escala materializada.

Caso seja necessária uma alteração posterior, ela deve seguir as regras de permissões, fechamento e autorização.

A análise posterior deve preservar a distinção entre:

* o que foi materializado;
* o que foi posteriormente identificado;
* eventual alteração autorizada;
* o resultado posterior.

---

## 6. Relação com jornadas

A análise de cobertura deve considerar os horários efetivamente abrangidos pelas jornadas.

Devem ser consideradas as características das jornadas definidas em `05-escalas-e-plantoes.md`, incluindo:

* SD;
* SN;
* DN;
* M;
* T;
* MT;
* jornadas especiais autorizadas.

Uma jornada de 24 horas, como DN, deve ser considerada em toda a sua abrangência temporal para fins de cobertura.

A equivalência de DN a duas jornadas de 12 horas para fins de contagem de carga não deve fazer com que o sistema considere dois servidores distintos para fins de cobertura.

---

## 7. Relação com lotação

A cobertura deve considerar os servidores efetivamente alocados ao setor conforme as regras de lotação.

Um servidor não deve ser considerado como cobertura válida de um setor apenas porque possui uma jornada registrada, quando sua alocação não for válida para aquele setor.

Atuações excepcionais em outro setor devem ser tratadas conforme as regras de APH quando aplicáveis.

---

## 8. Regime

O dimensionamento deve considerar as informações de regime aplicáveis ao servidor.

A análise não deve criar automaticamente uma jornada incompatível com o regime do servidor.

Alterações posteriores de regime não devem reescrever uma análise ou uma escala materializada de período anterior.

---

## 9. Conflitos

O sistema deve identificar situações em que a composição da escala produza conflito com a necessidade de cobertura ou com as regras de jornada.

Exemplos:

* dois servidores alocados para a mesma necessidade quando apenas um é necessário;
* quantidade inferior à necessária;
* período sem servidor;
* servidor alocado em período incompatível;
* sobreposição ou combinação inválida de jornadas.

A identificação de conflito não implica alteração automática da escala.

---

## 10. Automação

O sistema pode utilizar automação para:

* calcular cobertura;
* identificar insuficiências;
* identificar excessos;
* apontar conflitos;
* sugerir possíveis ajustes;
* destacar períodos críticos.

As sugestões são mecanismos de apoio à decisão.

A automação não deve substituir a decisão do responsável pela escala.

O sistema não deve alterar automaticamente uma escala materializada para corrigir uma situação de cobertura.

---

## 11. Histórico

Resultados relevantes do dimensionamento devem possuir rastreabilidade quando utilizados para decisões da escala.

Quando uma alteração posterior ocorrer em razão de uma insuficiência ou conflito identificado, deve ser possível distinguir:

* situação identificada;
* decisão tomada;
* alteração realizada;
* resultado posterior.

A alteração da escala não deve apagar o histórico da análise que motivou a decisão.

---

## 12. Regra para agentes

O agente de desenvolvimento deve tratar dimensionamento como mecanismo de análise e apoio à decisão.

O agente não deve:

* alterar automaticamente a escala para corrigir cobertura;
* criar necessidades de cobertura sem regra definida;
* inventar quantidade mínima de servidores;
* considerar uma jornada inválida como cobertura válida;
* tratar DN como dois servidores ou dois plantões independentes;
* ignorar a lotação na análise;
* inventar critérios de dimensionamento.

Quando a forma de cálculo ou a necessidade de cobertura não estiver definida, a situação deve ser registrada como pendência de negócio.

---

## 13. Relação com outros documentos

As regras de dimensionamento devem ser consideradas em conjunto com:

* `02-regras-de-negocio.md` — regras transversais;
* `04-cadastros-e-lotacoes.md` — servidores e lotações;
* `05-escalas-e-plantoes.md` — jornadas e escalas;
* `06-equipes-e-modelos.md` — mecanismos de planejamento;
* `07-intercorrencias-e-compensacoes.md` — ocorrências que possam afetar a cobertura;
* `09-fechamento-e-auditoria.md` — alterações posteriores;
* `10-relatorios.md` — apresentação dos resultados.

As regras específicas para cálculo do dimensionamento devem ser definidas antes da implementação do motor de cobertura.
