# Escalar — Visão do Produto

## 1. Identificação

**Nome:** Escalar
**Descrição:** Sistema de Gestão de Escalas Hospitalares

O Escalar é um sistema destinado à gestão das escalas hospitalares, contemplando servidores, lotações, jornadas, equipes, intercorrências, compensações, dimensionamento, fechamento, auditoria e relatórios.

O sistema deve substituir o uso operacional disperso de planilhas por uma estrutura centralizada, rastreável e baseada em regras de negócio.

---

## 2. Objetivo

O objetivo do Escalar é permitir que a instituição:

* mantenha o cadastro dos servidores;
* controle suas lotações;
* organize as equipes;
* planeje e materialize escalas mensais;
* aplique regras de jornada;
* registre intercorrências;
* controle faltas e compensações;
* acompanhe carga horária;
* avalie cobertura/dimensionamento;
* feche as escalas;
* preserve histórico;
* gere relatórios;
* mantenha rastreabilidade das alterações.

---

## 3. Abrangência

O sistema deve ser concebido para utilização em todo o hospital.

Cada setor/unidade pode possuir sua própria escala.

A estrutura deve permitir que um servidor pertença a um setor e, excepcionalmente, possa atuar em outro setor por meio de APH.

---

## 4. Princípio central

A regra fundamental do sistema é:

> **Automação propõe. O gestor decide. A escala materializada é a fonte da verdade.**

O sistema pode utilizar regras para sugerir, validar ou identificar conflitos.

A automação não deve substituir a decisão do responsável pela escala.

Depois de confirmada/materializada, a escala representa o que efetivamente foi definido para aquele período.

---

## 5. Escalas

As escalas são organizadas mensalmente.

O sistema deve trabalhar com o conceito de ciclo mensal.

A escala pode ser planejada, revisada, confirmada e posteriormente fechada.

---

## 6. Jornadas principais

As jornadas previamente definidas incluem:

### SD

07:00 às 19:00.

### SN

19:00 às 07:00.

### DN

24 horas, das 07:00 às 07:00 do dia seguinte.

Para fins de carga/jornada, DN corresponde a dois plantões de 12 horas.

### M

07:00 às 13:00.

### T

13:00 às 19:00.

### MT

Jornada configurável, podendo contemplar jornadas de 8 ou 10 horas, com horário de entrada e saída configuráveis.

---

## 7. Jornadas especiais

O sistema deve permitir jornadas/plantões especiais diferentes do padrão de 12 horas quando autorizados pela chefia.

Essas jornadas não devem ser criadas automaticamente.

A autorização da chefia é necessária.

---

## 8. Regra das 36 horas

O sistema deve impedir a programação incompatível com a regra estabelecida de descanso entre plantões.

A regra geral definida para o sistema é:

* mínimo de 12 horas entre plantões;
* jornadas de 36 horas são proibidas.

As regras de validação devem ser aplicadas antes da materialização da escala.

---

## 9. Carga horária

A referência ordinária de planejamento é de **120 horas mensais**.

Esse valor não deve ser tratado como um limite universal para todos os casos.

O sistema deve distinguir planejamento/carga ordinária de situações excepcionais, compensações, APH e outras situações previstas nas regras do domínio.

---

## 10. APH

APH representa atuação excepcional do servidor em outro setor.

O APH é tratado separadamente da carga ordinária.

APH **não compõe a carga horária ordinária** do servidor.

---

## 11. Intercorrências

Intercorrências devem poder ser registradas associadas a períodos específicos.

O registro deve possuir código e período.

Intercorrências não devem ser artificialmente mescladas em um único registro de um dia quando os períodos forem distintos.

---

## 12. Faltas e compensações

Faltas, licenças e férias devem ser consideradas no planejamento.

O sistema deve permitir o registro das ocorrências e das respectivas compensações quando aplicáveis.

Esses registros devem preservar o histórico e não apagar silenciosamente o planejamento original.

---

## 13. Dimensionamento e cobertura

O sistema deve permitir verificar a cobertura da escala em relação às necessidades do setor.

O dimensionamento deve considerar os servidores e jornadas efetivamente planejados/materializados.

A cobertura deve permitir identificar situações de insuficiência ou conflito.

---

## 14. Equipes e modelos

O sistema deve possuir conceito de equipes/modelos para facilitar a construção das escalas.

As equipes e padrões devem poder ser utilizados para aplicar uma estrutura de escala a partir do ingresso do servidor.

Uma alteração posterior na composição da equipe não deve reescrever automaticamente meses de escala já materializados.

---

## 15. Planejada x realizada

O sistema deve preservar a diferença entre:

* aquilo que foi planejado;
* aquilo que foi efetivamente materializado;
* ocorrências posteriores que alteraram a execução.

O histórico não deve ser destruído pela edição de dados atuais.

---

## 16. Fechamento

A escala possui ciclo de vida.

Depois de fechada:

* fica disponível para consulta;
* alterações posteriores exigem autorização;
* alterações autorizadas devem ser rastreadas.

A Divisão de Enfermagem possui papel de controle sobre alterações posteriores ao fechamento.

---

## 17. Auditoria

O sistema deve preservar rastreabilidade das alterações relevantes.

Deve ser possível identificar alterações importantes realizadas sobre escalas e registros relacionados.

---

## 18. Interface

A interface deve priorizar:

* leitura rápida;
* visão mensal;
* identificação clara dos servidores;
* identificação dos turnos;
* indicação de conflitos;
* distinção entre planejado e materializado;
* acesso às ocorrências;
* filtros por setor/unidade.

---

## 19. Regra para evolução

O agente de desenvolvimento não deve criar regras de negócio por inferência.

Quando uma decisão de negócio não estiver documentada, ela deve ser tratada como pendência de requisito.

---

## 20. Fonte da verdade

Este documento, juntamente com os demais documentos de regras de negócio do diretório `docs/`, representa a referência funcional do Escalar.

A implementação técnica pode evoluir sem alterar essas regras.

Alterações nas regras devem ser explicitamente aprovadas e documentadas. 
