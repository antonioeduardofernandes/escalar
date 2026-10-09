Visão do Produto — Escalar

1. Identificação

Nome: Escalar
Descrição: Sistema de Gestão de Escalas Hospitalares.

O Escalar é um sistema destinado a planejar, organizar, elaborar, validar, materializar, fechar, controlar, auditar e consultar escalas hospitalares, considerando servidores, unidades, jornadas, equipes, modelos de trabalho, ocorrências, compensações e dimensionamento de cobertura.

O sistema deve apoiar a gestão operacional das escalas, reduzindo trabalho manual, inconsistências, conflitos de jornada e dificuldades de acompanhamento do planejamento.

O Escalar não é, nesta etapa, um sistema de frequência, folha de pagamento, cálculo de remuneração ou gestão integral de recursos humanos.

2. Princípios fundamentais

O desenvolvimento e a operação do sistema devem respeitar os seguintes princípios:

1. Nós definimos. O agente registra e executa. As regras de negócio são decididas pelos responsáveis pelo projeto. O agente de desenvolvimento não pode inventar regras para preencher lacunas.
2. A automação propõe. O gestor decide. O sistema pode gerar sugestões, identificar inconsistências e apontar necessidades, mas não deve tomar decisões administrativas que dependam de autorização humana.
3. A escala materializada é a fonte da verdade do planejamento registrado. Alterações posteriores em cadastros, equipes, modelos, vigências ou calendários não podem modificar silenciosamente escalas materializadas.
4. Planejamento, materialização e realização são conceitos distintos. Uma jornada planejada ou materializada não representa, por si só, confirmação de comparecimento ou realização efetiva do trabalho.
5. Ocorrências não apagam o planejamento original. Faltas, licenças e outras ocorrências devem ser registradas sem eliminar o histórico do plantão originalmente planejado.
6. A APH é trabalho real, mas separado da escala ordinária. Deve ser identificada individualmente e considerada nas validações operacionais aplicáveis.
7. Regras não definidas são pendências. O agente deve registrar as lacunas e solicitar decisão humana antes de implementar comportamentos que dependam delas.
8. O cadastro de servidores é instrumental. Os dados cadastrais devem atender às necessidades de identificação operacional, elaboração das escalas, aplicação das regras, auditoria e relatórios, sem transformar o Escalar em um sistema de gestão de pessoas.
9. Simplicidade, segurança e rastreabilidade. Entre alternativas que atendam igualmente às necessidades operacionais, deve-se priorizar a solução mais simples, segura e auditável.
10. Nenhuma alteração relevante deve ocorrer silenciosamente. Mudanças que afetem escalas existentes devem ser identificadas e apresentadas para revisão, respeitando o estado da escala e as permissões do usuário.

2.1. Princípio de escopo e finalidade do Escalar

O Escalar tem como missão principal organizar, elaborar, validar, materializar, controlar, auditar e disponibilizar informações relacionadas às escalas hospitalares.

O cadastro de servidores é uma funcionalidade acessória, necessária para identificar os profissionais envolvidos nas escalas e aplicar as regras operacionais pertinentes. Ele não constitui a finalidade principal do sistema.

O Escalar não se destina a substituir sistemas de gestão de pessoas, administrar a trajetória funcional dos indivíduos ao longo da vida ou manter mecanismos de conciliação de identidades entre diferentes vínculos institucionais.

Para fins operacionais, cada matrícula corresponde a uma entidade "Servidor" independente. Uma mesma pessoa física poderá estar representada por entidades distintas quando possuir matrículas diferentes, sem necessidade de relacioná-las ou unificar seus históricos.

Os dados cadastrais e as funcionalidades relacionadas a servidores deverão atender às necessidades da gestão de escalas, da aplicação das regras de negócio, da auditoria e da geração de relatórios.

Novas funcionalidades cadastrais somente deverão ser incorporadas quando houver justificativa operacional clara e benefício direto para esses objetivos.

3. Objetivos do sistema

O Escalar deve permitir:

- manter o cadastro operacional dos servidores;
- organizar servidores em unidades e equipes administrativas;
- cadastrar e manter cargos e vínculos institucionais por meio de listas administráveis;
- configurar modelos de escala e suas vigências;
- sugerir o preenchimento de escalas a partir dos modelos vigentes;
- permitir ajustes manuais e exceções autorizadas;
- validar conflitos e intervalos entre jornadas;
- manter a escala ordinária e a APH identificáveis separadamente;
- registrar férias, licenças e faltas;
- controlar dívidas e quitações integrais de compensação;
- definir e acompanhar o dimensionamento da cobertura por unidade e turno;
- materializar, fechar e reabrir escalas conforme as permissões;
- preservar versões e o histórico das alterações relevantes;
- sinalizar impactos de mudanças cadastrais, operacionais e de calendário;
- acompanhar pendências, validações, conflitos e revisões;
- disponibilizar consultas e relatórios compatíveis com as permissões dos usuários;
- notificar os servidores afetados após a publicação de uma nova versão fechada da escala.

4. Escopo funcional

4.1. Cadastro de servidores

O cadastro operacional deve conter:

- matrícula, obrigatória, única e imutável após a criação;
- nome, obrigatório;
- e-mail, obrigatório;
- cargo, obrigatório e selecionado de uma lista administrável;
- vínculo institucional, obrigatório e selecionado de uma lista administrável;
- lotação principal;
- situação ativa ou inativa.

CPF e data de nascimento não fazem parte do cadastro do Escalar. Não haverá campo de nome social, função, categoria profissional ou regime independente.

A matrícula identifica uma entidade funcional independente dentro do sistema. Uma nova matrícula representa um novo cadastro, mesmo quando a pessoa física já estiver representada por outra matrícula. O Escalar não deverá implementar conciliação ou unificação de identidades entre matrículas diferentes.

Os cargos e vínculos institucionais são mantidos pelo Administrador. As opções de vínculo podem contemplar, conforme a lista administrada, Estatutário, Fiotec, Estado e contratos temporários identificados pelo respectivo certame, como 6º, 7º e 8º certames.

Matrícula, cargo e vínculo são imutáveis após a criação do cadastro. A correção de dados permitidos deve preservar a rastreabilidade.

Cada servidor possui uma única lotação principal vigente por vez. Alterações de lotação devem preservar o histórico e respeitar períodos de vigência sem sobreposição.

A atuação em APH em outra unidade não modifica, por si só, a lotação principal.

A inativação bloqueia o acesso do servidor e impede novas alocações, sem excluir o histórico nem cancelar automaticamente plantões existentes. A reativação não deve duplicar registros nem reinserir automaticamente o servidor em escalas anteriores.

4.2. Unidades

Unidade é o termo oficial utilizado no domínio e na interface do Escalar para identificar uma subdivisão organizacional do hospital.

Cada unidade pode possuir escalas próprias e configurações operacionais compatíveis com as funcionalidades do sistema.

As unidades são entidades estruturadas, não campos de texto livre. Podem ser criadas, editadas ou desativadas por usuários autorizados.

A desativação de uma unidade não deve apagar seu histórico nem modificar silenciosamente escalas existentes.

O termo “setor” não deve ser utilizado como nome oficial da entidade organizacional na interface, no glossário ou nos documentos de domínio do sistema.

4.3. Equipes

Uma equipe é um agrupamento administrativo de servidores que seguem um padrão de escala. Não representa necessariamente uma equipe clínica real.

Não haverá campo de líder ou responsável pela equipe.

Cada servidor pode pertencer a somente uma equipe por vez, sem sobreposição de vínculos. A relação entre servidor e equipe possui vigência individual.

A equipe não possui período de validade próprio. A vigência é controlada pelas relações entre servidores e equipes e pela aplicação dos modelos.

4.4. Modelos de escala

O modelo representa um ciclo parametrizado de trabalho e descanso.

Seus parâmetros devem permitir representar a duração do trabalho, o tipo de turno e o período de descanso, conforme o modelo aprovado.

O modelo não é uma lista arbitrária de dias da semana nem define, por si só, a quantidade de profissionais necessária para a cobertura.

A aplicação do modelo à equipe possui uma data final, prorrogável por Gestor ou Supervisor autorizado, conforme o âmbito de atuação. Cada servidor também possui sua própria vigência no vínculo com a equipe.

O sistema não deve gerar escalas indefinidamente.

Alterações nos modelos, nas vigências ou nos vínculos não podem modificar silenciosamente escalas já existentes.

4.5. Jornadas padrão

As jornadas padrão são:

Código| Horário| Duração
SD| 07h–19h| 12 horas
SN| 19h–07h do dia seguinte| 12 horas
DN| 07h–07h do dia seguinte| 24 horas
M| 07h–13h| 6 horas
T| 13h–19h| 6 horas

Jornadas especiais exigem parâmetros explicitamente definidos e aprovados.

O sistema deve sinalizar sobreposições, conflitos entre unidades, intervalos inferiores a 12 horas entre jornadas e sequências proibidas de 36 horas, conforme as regras institucionais.

A APH também está sujeita às validações temporais aplicáveis.

4.6. Plantonistas e diaristas

O sistema distingue plantonistas e diaristas conforme as regras operacionais e os dados necessários à elaboração da escala. Essa distinção não constitui um campo independente de regime no cadastro do servidor.

Para diaristas, o Gestor seleciona M ou T. O sistema gera os dias de segunda a sexta no período aplicável, excluindo sábados, domingos, feriados federais oficiais e datas institucionais adicionais cadastradas e vigentes.

Diaristas não estão sujeitos à referência mensal de 120 horas.

A referência de 120 horas mensais aplica-se ao planejamento ordinário dos plantonistas. SD e SN correspondem a 12 horas cada; DN corresponde a 24 horas. A APH não compõe essa referência.

4.7. Calendário de feriados e datas institucionais adicionais

O calendário oficial federal é a referência padrão para os feriados considerados pelo sistema.

O sistema não deve presumir que feriados estaduais, municipais ou pontos facultativos sejam automaticamente adotados pela instituição.

O Supervisor pode cadastrar datas institucionais adicionais, incluindo feriados estaduais ou municipais adotados pela instituição e pontos facultativos.

Cada registro de data adicional deve conter:

- nome;
- data;
- tipo;
- indicação de vigência ou ano de aplicação, quando aplicável.

Essas datas afetam a geração automática das escalas dos diaristas, não o funcionamento das escalas assistenciais. As escalas assistenciais continuam funcionando em sábados, domingos e feriados.

Alterações no calendário não podem apagar ou modificar silenciosamente escalas existentes. Quando uma mudança puder afetar uma escala, o sistema deve sinalizar os impactos para revisão e exigir ação explícita autorizada para qualquer alteração posterior.

4.8. APH

A APH é uma jornada adicional, identificada separadamente da escala ordinária.

Deve aparecer no calendário consolidado do servidor e permanecer visualmente distinguível.

A APH:

- é considerada trabalho real para validações de sobreposição, conflitos e intervalo mínimo entre jornadas;
- não integra a referência mensal de 120 horas ordinárias;
- pode ser contabilizada no dimensionamento, desde que o profissional seja elegível e esteja previsto para a unidade, turno e período considerados;
- não altera a lotação principal;
- não quita automaticamente uma dívida de compensação.

O sistema deve evitar contar duas vezes o mesmo servidor para a mesma cobertura temporal.

O Escalar não calcula pagamento ou remuneração de APH.

4.9. Ocorrências

As categorias de ocorrência incluem:

- férias;
- licenças;
- faltas.

Férias e licenças possuem períodos de início e fim. Os tipos e códigos de licença são configuráveis pelo Administrador, sem necessidade de alterar o código da aplicação para incluir novos tipos.

Uma falta deve ser vinculada a um plantão específico.

O Gestor classifica a falta como:

- sem compensação;
- com compensação.

Somente faltas classificadas como compensáveis geram dívida de horas.

A decisão de compensação pertence ao Gestor e pode considerar justificativas e tratativas administrativas realizadas fora do sistema.

O registro de uma ocorrência não apaga o plantão originalmente planejado nem altera silenciosamente uma escala materializada.

4.10. Compensações

A dívida corresponde à duração integral do plantão:

- SD ou SN: 12 horas;
- DN: 24 horas.

A compensação exige jornadas completas, sem quitação parcial.

Uma dívida de 12 horas exige uma jornada compensatória completa de 12 horas.

Uma dívida de 24 horas pode ser quitada por uma jornada completa de 24 horas ou por duas jornadas completas de 12 horas.

A simples inclusão de um plantão futuro não quita automaticamente a dívida. A quitação deve ser registrada explicitamente.

A APH não quita automaticamente dívidas de compensação.

O Escalar não é sistema de folha de pagamento. A compensação é um controle administrativo de horas.

4.11. Dimensionamento

O dimensionamento permite que o Gestor defina a quantidade de profissionais necessária para a cobertura de uma unidade em determinado período e turno.

A configuração inclui:

- unidade;
- período de vigência;
- turno diurno ou noturno;
- quantidade necessária;
- cargos elegíveis.

O sistema compara a necessidade com os profissionais contemplados no planejamento e identifica déficits, correspondências, excessos e conflitos.

A APH pode contar na cobertura quando o profissional for elegível e estiver contemplado na unidade, turno e período avaliados.

O dimensionamento não altera automaticamente a escala.

4.12. Geração sugerida de escalas

Ao iniciar a elaboração de uma escala mensal, o sistema deve permitir sugerir o preenchimento com base nos modelos vigentes e nas relações aplicáveis entre servidores e equipes.

A geração deve apresentar obrigatoriamente uma prévia antes de alterar a matriz.

A prévia deve apresentar, conforme aplicável:

- preenchimentos propostos;
- células já preenchidas que serão preservadas;
- conflitos bloqueantes;
- alertas que exigem análise;
- pendências relevantes identificadas pela validação.

Por padrão, a geração preenche apenas células vazias. A substituição de turnos existentes exige uma operação separada, prévia específica, revisão e confirmação explícita.

Conflitos bloqueantes devem ser resolvidos antes da aplicação integral de uma proposta que os contenha. Alertas devem ser apresentados separadamente, conforme a regra aplicável.

Se dados relevantes mudarem entre a geração da prévia e a confirmação, o sistema deve invalidar ou recalcular a prévia.

A aplicação confirmada salva as alterações permitidas, mas mantém a escala em elaboração. A geração não materializa nem fecha automaticamente a escala.

O mês anterior deve estar disponível para consulta e comparação durante a elaboração, sem cópia automática de turnos para o novo mês.

4.13. Validação e pendências

O sistema deve validar continuamente as alterações relevantes e oferecer uma validação completa antes da materialização.

A validação deve distinguir:

- bloqueios: violações de regras que impedem a operação correspondente;
- alertas: situações que exigem análise;
- pendências operacionais: tarefas necessárias para completar ou revisar a escala.

Cada pendência deve indicar o motivo e, quando aplicável, a unidade, o servidor, a data ou o turno afetado. Quando houver uma ação prevista nas regras, a interface deve permitir navegar até o ponto relevante da matriz.

Após correções, a situação deve ser atualizada mediante nova validação. O sistema deve manter o histórico de resoluções e reaberturas, sem apagar a rastreabilidade.

O sistema não deve inventar uma solução para regras ainda não definidas nem permitir que uma violação obrigatória seja ignorada apenas por ser apresentada como alerta.

Se a escala mudar depois da validação completa, o resultado anterior deve ser considerado desatualizado e a escala precisa ser validada novamente antes da materialização.

4.14. Alterações que afetam escalas existentes

Mudanças cadastrais, de lotação, de equipe, de modelo, de vigência, de calendário ou de ocorrência não podem apagar, substituir ou recalcular silenciosamente turnos existentes.

O sistema deve identificar e sinalizar escalas, servidores, datas ou turnos potencialmente afetados, permitindo que Gestor ou Supervisor, conforme as permissões e o âmbito de atuação, avalie os impactos e execute as alterações autorizadas.

Escalas materializadas ou fechadas possuem proteção adicional: sua versão oficial e seu histórico devem ser preservados. Alterações posteriores devem respeitar o fluxo de reabertura e revisão definido para o sistema.

4.15. Materialização

Materializar significa registrar os plantões concretos planejados para um período.

A materialização não confirma comparecimento nem realização efetiva do trabalho.

Antes da materialização, o sistema deve executar validação completa e impedir a operação quando houver bloqueios não resolvidos. Os alertas e as demais pendências devem ser apresentados conforme suas regras específicas.

A materialização registra a versão do planejamento, incluindo unidade, período, servidores, turnos, responsável, data, resultado da validação e informações necessárias à auditoria.

A escala materializada é a referência do planejamento registrado. Mudanças posteriores em cadastros, modelos, equipes, vínculos, vigências ou calendários não podem alterar silenciosamente seus registros.

Materialização não equivale a fechamento nem a publicação.

4.16. Fechamento, reabertura e publicação

Gestor e Supervisor podem materializar e fechar escalas dentro de seus respectivos âmbitos de atuação.

Somente Supervisor pode reabrir uma escala fechada, respeitando as autorizações aplicáveis. A reabertura exige justificativa obrigatória e registro de auditoria.

O fechamento exige confirmação explícita, nova validação no backend e verificação de que a versão a ser fechada não foi modificada desde a validação.

Uma escala fechada fica protegida contra edições operacionais comuns. A existência de uma ocorrência ou falta não impede automaticamente o fechamento.

A reabertura preserva a versão fechada anterior e seu histórico. Após a revisão, a escala deve ser validada novamente, materializada, se aplicável, e fechada antes da publicação de uma nova versão oficial.

O sistema deve permitir comparar versões, identificando turnos adicionados, removidos ou alterados e mudanças relevantes em carga horária, conflitos e dimensionamento.

Após o fechamento, o sistema deve iniciar a notificação dos servidores afetados por e-mail, com link seguro para consulta da própria escala. A falha no envio de e-mail não deve desfazer o fechamento.

O servidor consulta a versão atualmente publicada e pode, opcionalmente, baixar seu PDF. O sistema não envia PDFs anexados automaticamente a todos os servidores.

4.17. Histórico, auditoria e relatórios

O sistema deve preservar o histórico das operações relevantes, incluindo alterações cadastrais, materializações, fechamentos, reaberturas, ocorrências, decisões de compensação, quitações, mudanças de calendário e publicações de versões.

O modelo técnico de auditoria, os dados exatos de cada evento e a política de retenção serão definidos na etapa de arquitetura.

Os relatórios devem contemplar, conforme as permissões:

- escala individual;
- escala por unidade e período;
- jornadas ordinárias e APH;
- carga horária ordinária planejada;
- ocorrências e compensações;
- dívidas em aberto e quitações;
- dimensionamento e cobertura;
- déficits, correspondências, excessos e conflitos.

A APH deve permanecer identificável separadamente, inclusive nos relatórios consolidados.

Os formatos de exportação serão definidos na arquitetura e no planejamento de implementação.

5. Papéis e responsabilidades

O Escalar possui exatamente quatro papéis de usuário:

5.1. Administrador

Responsável pela manutenção administrativa e estrutural do sistema, incluindo usuários, acessos, permissões, unidades, cargos, vínculos institucionais, configurações administrativas e tipos e códigos de licença.

Pode criar, editar, desativar e reativar cadastros de servidores conforme as permissões administrativas definidas.

Não recebe automaticamente permissões operacionais para elaborar, materializar, fechar ou reabrir escalas.

5.2. Servidor

Pode consultar a própria escala e as informações disponibilizadas para sua visualização.

Não pode editar escalas, consultar dados restritos de outros servidores nem editar o próprio cadastro.

A consulta individual deve ser adequada a dispositivos móveis e pode oferecer download de PDF.

5.3. Gestor

Atua nas unidades atribuídas ao seu âmbito de atuação.

Pode elaborar e ajustar escalas abertas, configurar equipes e modelos, definir dimensionamento, registrar ocorrências, decidir se uma falta específica será compensável, materializar e fechar escalas dentro das regras autorizadas.

Pode prorrogar a vigência de aplicação dos modelos dentro das regras autorizadas.

Não pode criar, editar, desativar ou reativar cadastros de servidores. Não pode reabrir uma escala fechada.

5.4. Supervisor

Atua nas unidades autorizadas ao seu âmbito.

Pode criar, editar, desativar e reativar cadastros de servidores, respeitando as regras de imutabilidade e o histórico.

Pode executar as operações de escala autorizadas ao seu papel, incluindo materialização, fechamento e reabertura de escalas dentro do âmbito permitido.

Pode cadastrar feriados institucionais adicionais e pontos facultativos.

A designação “Divisão de Enfermagem” representa uma unidade organizacional, não um papel adicional do sistema. Usuários lotados nessa unidade devem receber um dos quatro papéis existentes e as permissões correspondentes.

6. Fechamento e auditoria

O sistema deve preservar o histórico das operações relevantes, incluindo:

- alterações cadastrais e de lotação;
- alterações em equipes, modelos e calendários;
- geração e aplicação de propostas de escala;
- validações e pendências;
- materialização;
- fechamento e reabertura;
- alterações posteriores autorizadas;
- decisões de compensação e quitação de dívidas;
- publicação e notificação de versões.

A implementação deve preservar a possibilidade de compreender as operações realizadas e não pode apagar silenciosamente estados anteriores.

O modelo técnico da auditoria, os dados exatos de cada evento e a política de retenção serão definidos na etapa de arquitetura.

7. Limites do produto

Nesta etapa, o Escalar não deve ser tratado como:

- sistema de frequência;
- sistema de folha de pagamento;
- calculadora de remuneração;
- sistema integral de gestão de recursos humanos;
- sistema de avaliação de produtividade;
- mecanismo de conciliação de identidades entre matrículas distintas;
- mecanismo de alteração automática de escalas sem autorização.

Funcionalidades adicionais dependem de decisão explícita de escopo.

8. Regra para desenvolvimento

O agente de desenvolvimento deve implementar somente comportamentos apoiados em regras de negócio aprovadas.

Quando uma regra estiver ausente, ambígua ou contraditória, deve registrar a pendência e solicitar decisão humana.

O agente não pode inventar regras, permissões, exceções ou comportamentos para completar a implementação.

A arquitetura técnica deve respeitar os princípios e as regras descritos nesta visão do produto e nos documentos funcionais específicos aprovados.