# Visão do Produto — Escalar

## 1. Identificação

**Nome:** Escalar

**Descrição:** Sistema de Gestão de Escalas Hospitalares.

O Escalar é um sistema para planejar, organizar, validar, materializar, fechar e consultar escalas hospitalares, considerando servidores, setores, jornadas, equipes, modelos de trabalho, ocorrências, compensações e dimensionamento de cobertura.

O sistema deve apoiar a gestão operacional de escalas, reduzindo trabalho manual, inconsistências e conflitos de jornada.

O Escalar não é, nesta etapa, um sistema de frequência, folha de pagamento ou cálculo de remuneração.

## 2. Princípios fundamentais

O desenvolvimento e a operação do sistema devem respeitar estes princípios:

1. **Nós definimos. O agente registra e executa.** As regras de negócio são decididas pelos responsáveis pelo projeto. O agente de desenvolvimento não pode inventar regras para preencher lacunas.
2. **A automação propõe. O gestor decide.** O sistema pode gerar sugestões, identificar inconsistências e apontar necessidades, mas não deve tomar decisões administrativas que dependam de autorização humana.
3. **A escala materializada é a fonte da verdade do planejamento registrado.** Alterações posteriores em cadastros, modelos, vigências ou calendários não podem modificar silenciosamente escalas materializadas.
4. **Planejamento, materialização e realização são conceitos distintos.** Uma jornada planejada não representa, por si só, confirmação de comparecimento ou realização efetiva.
5. **Ocorrências não apagam o planejamento original.** Faltas, licenças e outras ocorrências devem ser registradas sem eliminar o histórico do plantão originalmente planejado.
6. **A APH é trabalho real, mas separado da escala ordinária.** Deve ser identificada individualmente e considerada nas validações operacionais aplicáveis.
7. **Regras não definidas são pendências.** O agente deve registrá-las e solicitar decisão humana antes de implementar comportamentos que dependam delas.

## 3. Objetivos do sistema

O Escalar deve permitir:

* manter o cadastro dos servidores e suas informações funcionais;
* organizar servidores em equipes administrativas;
* configurar modelos de escala e suas vigências;
* gerar escalas de diaristas e plantonistas conforme as regras aplicáveis;
* validar conflitos e intervalos entre jornadas;
* manter a escala ordinária e a APH identificáveis separadamente;
* registrar férias, licenças e faltas;
* controlar dívidas e quitações integrais de compensação;
* definir e acompanhar o dimensionamento da cobertura por setor e turno;
* materializar, fechar e reabrir escalas conforme as permissões;
* preservar o histórico das alterações relevantes;
* disponibilizar consultas e relatórios compatíveis com as permissões dos usuários.

## 4. Escopo funcional

### 4.1. Cadastro de servidores

O cadastro deve conter os seguintes campos obrigatórios de identificação:

* matrícula;
* nome;
* CPF;
* e-mail;
* situação ativa ou inativa.

A data de nascimento é opcional. Não haverá campo de nome social.

Os dados funcionais são:

* cargo;
* vínculo;
* regime;
* lotação principal.

Não haverá campos separados de função ou categoria profissional.

A matrícula é única por servidor e funciona como identificador institucional e do sistema.

Os vínculos possíveis são:

* Ministério da Saúde;
* Fiotec;
* Estado;
* contrato temporário, com identificação do certame, como 6º, 7º ou 8º certame.

Cada servidor possui uma única lotação principal vigente por vez. Uma transferência encerra a lotação anterior e inicia a nova, sem sobreposição de períodos.

A atuação em APH em outro setor não modifica a lotação principal.

A inativação não exclui o histórico nem cancela automaticamente plantões já materializados. A reativação não pode duplicar registros existentes.

### 4.2. Equipes

Uma equipe é um agrupamento administrativo de servidores que seguem um padrão de escala. Não representa necessariamente uma equipe clínica real.

Não haverá campo de líder ou responsável pela equipe.

Cada servidor pode pertencer a somente uma equipe por vez, sem sobreposição de vínculos. A relação entre servidor e equipe possui vigência individual.

### 4.3. Modelos de escala

O modelo representa um ciclo parametrizado de trabalho e descanso.

Seus parâmetros devem permitir representar a duração do trabalho, o tipo de turno e o período de descanso, conforme o modelo aprovado.

O modelo não é uma lista arbitrária de dias da semana nem define, por si só, a quantidade de profissionais necessários para a cobertura.

A aplicação do modelo à equipe possui uma data final, prorrogável pelo gestor autorizado. Cada servidor também possui sua própria vigência no vínculo com a equipe.

O sistema não deve gerar escalas indefinidamente.

Alterações nos modelos, nas vigências ou nos vínculos não podem modificar silenciosamente escalas já materializadas.

### 4.4. Jornadas padrão

As jornadas padrão são:

| Código | Horário                 |  Duração |
| ------ | ----------------------- | -------: |
| SD     | 07h–19h                 | 12 horas |
| SN     | 19h–07h do dia seguinte | 12 horas |
| DN     | 07h–07h do dia seguinte | 24 horas |
| M      | 07h–13h                 |  6 horas |
| T      | 13h–19h                 |  6 horas |

Jornadas especiais exigem parâmetros explicitamente definidos e aprovados.

O sistema deve sinalizar sobreposições, conflitos entre setores, intervalos inferiores a 12 horas entre jornadas e sequências proibidas de 36 horas, conforme a regra institucional.

A APH também está sujeita às validações temporais aplicáveis.

### 4.5. Plantonistas e diaristas

O sistema distingue plantonistas e diaristas.

Para diaristas, o gestor seleciona M ou T. O sistema gera automaticamente os dias de segunda a sexta no período aplicável, excluindo sábados, domingos, feriados federais oficiais e datas institucionais adicionais cadastradas e vigentes.

Diaristas não estão sujeitos à referência mensal de 120 horas.

A referência de 120 horas mensais aplica-se ao planejamento ordinário dos plantonistas. SD e SN correspondem a 12 horas cada; DN corresponde a 24 horas. A APH não compõe essa referência.

### 4.6. Calendário de feriados e pontos facultativos

O calendário oficial federal é a referência padrão para os feriados considerados pelo sistema.

O sistema não deve presumir que feriados estaduais, municipais ou pontos facultativos sejam automaticamente adotados pela instituição.

O Supervisor pode cadastrar datas institucionais adicionais, incluindo feriados estaduais ou municipais adotados pela instituição e pontos facultativos.

Cada registro de data adicional deve conter:

* nome;
* data;
* tipo;
* indicação de vigência ou ano de aplicação, quando aplicável.

O cadastro deve deixar claro que essas datas afetam a geração automática das escalas dos diaristas, não o funcionamento das escalas assistenciais.

As escalas assistenciais continuam funcionando em sábados, domingos e feriados.

Alterações no calendário não podem apagar ou modificar silenciosamente escalas já materializadas. Quando uma mudança puder afetar escalas existentes, o sistema deve informar o usuário e exigir uma ação explícita autorizada para qualquer alteração posterior.

### 4.7. APH

A APH é uma jornada adicional, identificada separadamente da escala ordinária.

Deve aparecer no calendário consolidado do servidor e permanecer visualmente distinguível.

A APH:

* é considerada trabalho real para validações de sobreposição, conflitos e intervalo mínimo entre jornadas;
* não integra a referência mensal de 120 horas ordinárias;
* pode ser contabilizada na quantidade de profissionais contemplados no dimensionamento, desde que o profissional seja elegível e esteja previsto para o setor, turno e período considerados;
* não altera a lotação principal;
* não deve quitar automaticamente uma dívida de compensação.

O Escalar não calcula pagamento ou remuneração de APH.

### 4.8. Ocorrências

As categorias de ocorrência são:

* férias;
* licenças;
* faltas.

Férias e licenças possuem períodos de início e fim. Os tipos e códigos de licença são configuráveis pelo Administrador, sem necessidade de alterar o código da aplicação para incluir novos tipos.

Uma falta deve ser vinculada a um plantão específico.

O gestor classifica a falta como:

* sem compensação;
* com compensação.

Somente faltas classificadas como compensáveis geram dívida de horas.

A decisão de compensação pertence ao gestor e pode considerar justificativas e tratativas administrativas realizadas fora do sistema.

### 4.9. Compensações

A dívida corresponde à duração integral do plantão:

* SD ou SN: 12 horas;
* DN: 24 horas.

A compensação exige jornadas completas, sem quitação parcial.

Uma dívida de 12 horas exige uma jornada compensatória completa de 12 horas.

Uma dívida de 24 horas pode ser quitada por uma jornada completa de 24 horas ou por duas jornadas completas de 12 horas.

A simples inclusão de um plantão futuro não quita automaticamente a dívida. A quitação deve ser registrada explicitamente.

A APH não quita automaticamente dívidas de compensação.

O Escalar não é sistema de folha de pagamento. A compensação é um controle administrativo de horas.

### 4.10. Dimensionamento

O dimensionamento permite que o gestor defina a quantidade de profissionais necessária para a cobertura de um setor em determinado período e turno.

A configuração inclui:

* setor;
* período de vigência;
* turno diurno ou noturno;
* quantidade necessária;
* cargos elegíveis.

O sistema compara a necessidade com os profissionais contemplados no planejamento e identifica déficits, correspondências, excessos e conflitos.

A APH pode contar na cobertura quando o profissional for elegível e estiver contemplado no setor, turno e período avaliados.

O sistema deve evitar contar duas vezes o mesmo servidor para a mesma cobertura temporal.

A inclusão de APH no dimensionamento não significa incluir suas horas na referência mensal ordinária de 120 horas.

O dimensionamento não altera automaticamente a escala.

### 4.11. Materialização

Materializar significa registrar os plantões concretos planejados para um período.

Materialização não confirma comparecimento nem realização efetiva do trabalho.

A escala materializada é a referência do planejamento registrado. Mudanças posteriores em cadastros, modelos, vínculos, vigências ou calendários não podem alterar silenciosamente seus registros.

Quando uma alteração puder afetar escalas materializadas, o sistema deve informar o usuário e exigir uma ação explícita autorizada para qualquer alteração posterior.

### 4.12. Fechamento e reabertura

O fechamento indica que o planejamento de uma escala foi considerado finalizado.

Gestor e Supervisor podem materializar e fechar escalas dentro de seus respectivos escopos.

O Supervisor possui acesso a todos os setores.

Somente Supervisor e Divisão de Enfermagem podem reabrir escalas fechadas.

A Divisão de Enfermagem possui acesso a todos os setores e pode reabrir escalas fechadas. As permissões operacionais adicionais desse papel ainda precisam ser definidas explicitamente; não se deve presumir que sejam iguais às do Supervisor.

A reabertura não apaga o fechamento anterior nem o histórico da escala.

A existência de uma ocorrência ou falta não impede automaticamente o fechamento.

## 5. Papéis e responsabilidades

### Administrador

Responsável pela manutenção administrativa e estrutural do sistema, incluindo usuários, configurações administrativas, cadastros estruturais e tipos e códigos de licença.

Não recebe automaticamente permissões operacionais de gestor de escala.

### Servidor

Pode consultar a própria escala e as informações disponibilizadas para sua visualização. Não pode editar escalas nem acessar dados restritos de outros servidores.

### Gestor

Atua nos setores atribuídos ao seu escopo.

Pode planejar e ajustar escalas abertas, configurar equipes e modelos, definir dimensionamento, registrar ocorrências, decidir se uma falta específica será compensável, materializar e fechar escalas.

Pode prorrogar a vigência de aplicação dos modelos dentro das regras autorizadas.

Não pode reabrir uma escala fechada.

### Supervisor

Possui acesso operacional a todos os setores.

Pode editar escalas dentro das regras institucionais, materializar, fechar e reabrir escalas, além de cadastrar feriados institucionais adicionais e pontos facultativos.

### Divisão de Enfermagem

Possui acesso a todos os setores e pode reabrir escalas fechadas.

As permissões operacionais adicionais desse papel não devem ser presumidas. Permanecem pendentes de definição explícita.

## 6. Fechamento e auditoria

O sistema deve preservar o histórico das operações relevantes, incluindo materialização, fechamento, reabertura, alterações de escalas, alterações do calendário, decisões de compensação e quitação de dívidas.

O modelo técnico da auditoria, os dados exatos de cada evento e a política de retenção serão definidos na etapa de arquitetura.

A implementação deve preservar a possibilidade de compreender as operações realizadas e não pode apagar silenciosamente estados anteriores.

## 7. Relatórios

O sistema deve oferecer consultas e relatórios compatíveis com as permissões dos usuários, incluindo:

* escala individual;
* escala por setor e período;
* jornadas ordinárias e APH;
* carga horária ordinária planejada;
* ocorrências e compensações;
* dívidas em aberto e quitações;
* dimensionamento e cobertura;
* déficits, correspondências, excessos e conflitos.

A APH deve permanecer identificável separadamente nos relatórios, mesmo quando apresentada junto com a escala ordinária.

Os formatos de exportação serão definidos na arquitetura e no planejamento de implementação.

## 8. Limites do produto

Nesta etapa, o Escalar não deve ser tratado como:

* sistema de frequência;
* sistema de folha de pagamento;
* calculadora de remuneração;
* sistema de avaliação de produtividade;
* mecanismo de alteração automática de escalas sem autorização.

Funcionalidades adicionais dependem de decisão explícita de escopo.

## 9. Regra para desenvolvimento

O agente de desenvolvimento deve implementar somente comportamentos apoiados em regras de negócio aprovadas.

Quando uma regra estiver ausente, ambígua ou contraditória, deve registrar a pendência e solicitar decisão humana.

O agente não pode inventar regras, permissões, exceções ou comportamentos para completar a implementação.

A arquitetura técnica deve respeitar os princípios e as regras descritos nesta visão do produto.