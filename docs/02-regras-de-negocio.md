Escalar — Regras de Negócio

1. Regra central

«Automação propõe. O gestor decide. A escala materializada é a fonte da verdade do planejamento registrado.»

Nenhum algoritmo de geração automática pode substituir uma decisão explícita do responsável pela escala.

O sistema pode sugerir alocações, identificar conflitos, validar regras e apontar insuficiências, mas não deve alterar silenciosamente uma decisão já tomada nem contornar uma regra impeditiva.

2. Escopo deste documento

Este documento consolida as regras de negócio centrais e transversais do Escalar.

As regras específicas de cada domínio devem ser detalhadas nos documentos correspondentes, evitando duplicação ou interpretações divergentes.

Quando houver conflito entre uma regra geral deste documento e uma regra específica posteriormente aprovada para determinado domínio, a inconsistência deve ser identificada e resolvida antes da implementação.

Uma decisão de negócio que ainda não tenha sido definida não deve ser inventada para completar a implementação.

3. Escopo e finalidade do produto

A missão principal do Escalar é organizar, elaborar, validar, materializar, controlar, auditar e disponibilizar informações relacionadas às escalas hospitalares.

O cadastro de servidores é acessório e instrumental. Deve atender às necessidades de identificação operacional, elaboração das escalas, aplicação das regras de negócio, auditoria e geração de relatórios.

O Escalar não substitui sistemas de gestão de pessoas e não mantém uma identidade permanente da pessoa física ao longo de diferentes vínculos institucionais.

Cada matrícula corresponde a uma entidade "Servidor" independente. Matrículas diferentes podem representar a mesma pessoa física sem que o sistema precise relacionar ou unificar esses registros.

Entre alternativas que atendam igualmente às necessidades operacionais, deve-se priorizar a solução mais simples, segura e auditável.

4. Servidor e identificação

A matrícula é a identificação única do servidor no Escalar.

Deve existir apenas um cadastro para cada matrícula. A matrícula é obrigatória, única e imutável após a criação.

Os dados cadastrais operacionais são:

- matrícula;
- nome;
- e-mail;
- cargo;
- vínculo institucional;
- lotação principal;
- situação ativa ou inativa.

CPF e data de nascimento não fazem parte do cadastro. Não existe campo de nome social, função, categoria profissional ou regime independente.

Cargo e vínculo institucional são selecionados de listas administráveis. Somente o Administrador pode manter essas listas.

Uma nova matrícula representa uma nova entidade "Servidor", ainda que a pessoa física já esteja cadastrada sob outra matrícula.

Cargo e vínculo institucional são imutáveis após a criação do cadastro. As regras para correção de erros nesses campos devem preservar a integridade e a rastreabilidade dos registros. Não se deve criar um mecanismo de conciliação entre matrículas.

As alterações cadastrais permitidas devem preservar o histórico quando necessário para compreender registros anteriores.

A estrutura detalhada do cadastro de servidores deve ser definida em "04-cadastros-e-lotacoes.md".

5. Papéis, permissões e âmbito de atuação

O Escalar possui exatamente quatro papéis:

- Administrador;
- Servidor;
- Gestor;
- Supervisor.

O papel define o que o usuário pode fazer. O âmbito de atuação define em quais unidades pode executar essas ações.

As permissões devem ser verificadas no backend, não apenas pela exibição ou ocultação de opções na interface.

O Administrador mantém a estrutura administrativa e as configurações autorizadas, mas não recebe automaticamente permissões operacionais de gestão de escalas.

O Servidor consulta apenas a própria escala e as informações autorizadas para sua visualização.

O Gestor atua nas unidades de seu âmbito, podendo executar as operações de escala autorizadas, mas não pode criar, editar, desativar ou reativar servidores.

O Supervisor pode manter cadastros de servidores e executar operações de escala autorizadas, dentro do âmbito permitido. É o único papel autorizado a reabrir escalas fechadas.

A Divisão de Enfermagem é uma unidade organizacional, não um papel. Usuários dessa unidade devem possuir um dos quatro papéis definidos.

O detalhamento das permissões deve permanecer em "03-permissoes-e-papeis.md".

6. Lotação

A lotação representa a vinculação operacional principal do servidor a uma unidade.

Cada servidor possui uma única lotação principal vigente por vez. A lotação deve manter histórico de períodos, sem sobreposição.

A alteração da lotação deve preservar a informação anterior e respeitar sua vigência.

A atuação em APH em outra unidade não altera, por si só, a lotação principal.

A lotação deve ser considerada nas regras de alocação e validação da escala. Alterações de lotação não podem reescrever silenciosamente escalas existentes.

As regras detalhadas de cadastro, alteração e vigência das lotações devem ser definidas em "04-cadastros-e-lotacoes.md".

7. Escala mensal

A escala é organizada por unidade e período mensal.

Seu ciclo operacional contempla, conforme aplicável:

1. início da elaboração;
2. geração de proposta e revisão;
3. ajustes manuais;
4. validação;
5. materialização;
6. fechamento;
7. publicação;
8. eventuais alterações posteriores autorizadas, com reabertura quando exigida.

A escala materializada representa o planejamento registrado para aquele período. A materialização não deve ser confundida com a realização efetiva dos plantões.

A publicação comunica a versão oficial aos servidores e não substitui os registros de materialização ou fechamento.

8. Planejada, materializada e realizada

O Escalar deve distinguir:

- Planejada: a escala em elaboração, sujeita a ajustes e validações.
- Materializada: o planejamento concreto registrado como uma versão da escala.
- Realizada: o trabalho que efetivamente ocorreu, conforme as informações registradas no sistema.

Esses conceitos não são equivalentes.

Uma alteração posterior na execução não deve apagar ou reescrever silenciosamente a informação anteriormente planejada ou materializada.

Ocorrências posteriores devem ser registradas de modo que seja possível compreender a diferença entre o planejamento original, a versão materializada e o que efetivamente ocorreu.

9. Jornadas e plantões

Os plantões devem obedecer às regras de jornada estabelecidas pelo Escalar.

As jornadas padrão são:

Código| Horário| Duração
SD| 07h–19h| 12 horas
SN| 19h–07h do dia seguinte| 12 horas
DN| 07h–07h do dia seguinte| 24 horas
M| 07h–13h| 6 horas
T| 13h–19h| 6 horas

Entre as regras gerais:

- deve ser respeitado o intervalo mínimo de 12 horas entre jornadas, conforme as regras aplicáveis;
- sequências proibidas de 36 horas devem ser impedidas;
- sobreposições e combinações incompatíveis de jornadas devem ser identificadas e impedidas quando constituírem violações obrigatórias;
- jornadas especiais somente podem existir quando seus parâmetros tiverem sido explicitamente aprovados;
- conflitos entre unidades e entre escala ordinária e APH devem ser considerados nas validações temporais.

Os tipos de jornada, horários, equivalências e regras detalhadas de combinação devem ser definidos em "05-escalas-e-plantoes.md".

10. Carga horária ordinária

A referência de planejamento ordinário é de 120 horas mensais para plantonistas.

Essa referência não é um limite universal aplicável indistintamente a todos os servidores e situações.

Para essa referência:

- SD corresponde a 12 horas;
- SN corresponde a 12 horas;
- DN corresponde a 24 horas;
- APH não integra a carga horária ordinária;
- diaristas não estão sujeitos à referência mensal de 120 horas.

A carga horária apresentada no Escalar representa planejamento de jornada, não cálculo de frequência, folha de pagamento ou remuneração.

As regras detalhadas de apuração devem ser definidas nos documentos específicos de escalas, jornadas e APH.

11. APH

APH representa uma jornada adicional, separada da escala ordinária.

APH não altera, por si só, a lotação principal do servidor e não compõe a referência de 120 horas ordinárias.

APH é trabalho real e deve ser considerada nas validações de sobreposição, intervalo mínimo e demais regras temporais aplicáveis.

APH pode ser contabilizada no dimensionamento quando o profissional for elegível e estiver previsto para a unidade, turno e período avaliados.

O sistema deve evitar contar duas vezes o mesmo servidor para a mesma cobertura temporal.

APH não quita automaticamente dívidas de compensação.

O Escalar não calcula pagamento ou remuneração de APH. As regras detalhadas devem permanecer nos documentos específicos do domínio.

12. Equipes e modelos

Equipes e modelos facilitam a construção das escalas, mas não substituem a decisão do responsável.

A equipe é um agrupamento administrativo. Cada servidor pode pertencer a apenas uma equipe por vez, e cada relação servidor-equipe possui sua própria vigência.

A aplicação do modelo a uma equipe possui período de vigência e data final. O sistema não deve gerar escalas indefinidamente.

Uma alteração posterior em equipe, modelo ou vigência não deve reescrever automaticamente escalas existentes, sobretudo versões materializadas ou fechadas.

A escala materializada prevalece como registro do planejamento efetivamente confirmado para o período, mesmo que o modelo utilizado seja posteriormente alterado.

As regras detalhadas devem permanecer em "06-equipes-e-modelos.md".

13. Geração sugerida da escala mensal

Ao iniciar a elaboração de um novo mês, o sistema deve permitir sugerir o preenchimento com base nos modelos vigentes e nas relações aplicáveis entre servidores e equipes.

A geração deve apresentar uma prévia obrigatória antes de modificar a matriz.

A prévia deve identificar:

- turnos propostos;
- células já preenchidas que serão preservadas;
- conflitos bloqueantes;
- alertas para análise;
- pendências relevantes identificadas.

Por padrão, a aplicação da proposta preenche apenas células vazias. A substituição de turnos existentes exige prévia específica, revisão e confirmação explícita.

Conflitos bloqueantes devem ser resolvidos antes da aplicação integral de uma proposta que os contenha. Alertas devem ser apresentados separadamente conforme as regras aplicáveis.

Se dados relevantes mudarem entre a prévia e a confirmação, a proposta deve ser invalidada ou recalculada.

A confirmação aplica somente as alterações permitidas e mantém a escala em elaboração. Não materializa nem fecha automaticamente a escala.

O mês anterior deve estar disponível para consulta e comparação, sem cópia automática de turnos para o novo mês.

14. Validação, conflitos e pendências

A validação deve distinguir três categorias:

1. Bloqueios: violações de regras que impedem a operação correspondente.
2. Alertas: situações que exigem análise, sem serem automaticamente classificadas como violações impeditivas.
3. Pendências operacionais: tarefas necessárias para concluir ou revisar a escala, como células vazias ou alterações que precisam de análise.

A classificação deve decorrer das regras de negócio aprovadas. O sistema não pode reclassificar uma violação obrigatória como simples alerta para permitir a continuidade da operação.

A validação deve ocorrer durante as alterações relevantes e de forma completa antes da materialização.

A validação incremental pode atualizar rapidamente os indicadores afetados, mas a validação definitiva do backend é obrigatória para operações críticas.

Após uma correção, a situação deve ser atualizada mediante nova validação. A lista de pendências deve refletir o estado validado mais recente e preservar o histórico de resoluções e reaberturas.

Se a escala mudar após uma validação completa, o resultado anterior deve ser considerado desatualizado.

As regras detalhadas de fechamento, auditoria e relatórios devem ser mantidas nos documentos específicos correspondentes.

15. Alterações posteriores e preservação do planejamento

Mudanças em cadastro, lotação, equipes, modelos, vigências, calendário ou ocorrências não podem apagar, substituir ou recalcular silenciosamente turnos existentes.

O sistema deve identificar e sinalizar as escalas, os servidores, as datas ou os turnos potencialmente afetados.

Gestor ou Supervisor, conforme o papel, as permissões e o âmbito de atuação, deve analisar o impacto e realizar as alterações autorizadas.

Escalas materializadas ou fechadas possuem proteção adicional. Sua versão oficial e seu histórico devem ser preservados. Alterações posteriores devem respeitar o estado da escala e o fluxo de reabertura aplicável.

A desativação de um servidor impede novas alocações, preserva o histórico e sinaliza escalas em elaboração que possam ter sido afetadas. Não cancela automaticamente plantões existentes.

A reativação não reinclui automaticamente o servidor em escalas anteriores.

16. Ocorrências

Faltas, licenças, férias e outras ocorrências aplicáveis devem ser registradas quando fizerem parte do processo de gestão da escala.

Férias e licenças possuem períodos de início e fim. Uma falta deve estar vinculada a um plantão específico.

As ocorrências devem preservar o planejamento original e permitir identificar o período e os efeitos registrados.

O registro de uma ocorrência não apaga o plantão originalmente planejado nem reescreve silenciosamente uma escala materializada.

Os efeitos de cada tipo de ocorrência sobre planejamento, execução, carga horária e compensação devem ser definidos em "07-intercorrencias-e-compensacoes.md".

17. Compensações

Uma falta pode ser classificada pelo Gestor como sem compensação ou com compensação.

Somente uma falta classificada como compensável gera dívida de horas.

A dívida corresponde à duração integral do plantão original:

- SD ou SN: 12 horas;
- DN: 24 horas.

A compensação exige jornadas completas, sem quitação parcial. Uma dívida de 12 horas exige uma jornada completa de 12 horas. Uma dívida de 24 horas pode ser quitada por uma jornada completa de 24 horas ou por duas jornadas completas de 12 horas.

A inclusão de um plantão futuro não quita automaticamente a dívida. A quitação deve ser registrada explicitamente.

APH não quita automaticamente dívidas de compensação.

A compensação é um controle administrativo de horas, não um cálculo de folha de pagamento. As regras detalhadas devem permanecer em "07-intercorrencias-e-compensacoes.md".

18. Materialização

Materializar significa registrar os plantões concretos planejados para um período.

A materialização exige validação completa e não deve prosseguir enquanto houver bloqueios impeditivos não resolvidos.

A operação deve registrar a versão do planejamento, incluindo unidade, período, servidores, turnos, responsável, data e resultado da validação, além das informações necessárias à auditoria.

Materialização não confirma a realização efetiva do trabalho e não equivale a fechamento ou publicação.

Depois de materializada, a versão deve permanecer preservada. Alterações posteriores em cadastros, equipes, modelos, vigências ou calendários não podem reescrever silenciosamente seus registros.

19. Fechamento, reabertura e publicação

Gestor e Supervisor podem materializar e fechar escalas dentro de seus respectivos âmbitos de atuação.

Somente Supervisor pode reabrir uma escala fechada, respeitando as permissões aplicáveis. A reabertura exige justificativa e registro de auditoria.

O fechamento exige confirmação explícita, validação atualizada no backend e verificação de que a versão não mudou desde a validação.

A escala fechada fica protegida contra edições operacionais comuns. A existência de uma ocorrência ou falta não impede automaticamente o fechamento.

A reabertura não apaga a versão fechada anterior. A versão revisada deve passar novamente pelo processo de validação, materialização, quando aplicável, fechamento e publicação.

O sistema deve permitir comparar versões, identificando turnos adicionados, removidos ou alterados e mudanças relevantes de carga horária, conflitos e dimensionamento.

Após o fechamento, o sistema inicia a notificação dos servidores afetados por e-mail, com link seguro para consultar a própria escala. Falha no envio de e-mail não desfaz o fechamento.

As regras detalhadas devem permanecer em "09-fechamento-e-auditoria.md".

20. Histórico e rastreabilidade

Alterações relevantes nos dados e nas escalas devem preservar histórico quando sua natureza exigir rastreabilidade.

O sistema deve permitir distinguir, conforme aplicável:

- estado anterior e posterior;
- responsável pela operação;
- data e hora;
- motivo da reabertura, quando aplicável;
- versões materializadas e fechadas;
- alterações cadastrais e de lotação;
- geração, aplicação e revisão de propostas;
- validações e pendências;
- ocorrências, decisões de compensação e quitações;
- publicações e notificações.

O modelo técnico de auditoria, os dados exatos de cada evento e a política de retenção serão definidos na etapa de arquitetura.

O sistema não deve apagar silenciosamente decisões anteriormente materializadas.

21. Consistência

O sistema deve impedir ou sinalizar situações incompatíveis com regras de negócio já definidas, incluindo:

- duplicidade de matrícula;
- nova alocação de servidor inativo;
- incompatibilidade de alocação com as regras de lotação;
- sobreposição de jornadas;
- intervalo inferior ao mínimo permitido;
- sequências proibidas de 36 horas;
- combinações incompatíveis de jornadas;
- conflitos entre escala ordinária e APH;
- insuficiências ou excessos de cobertura;
- alterações não autorizadas em escalas materializadas ou fechadas.

A validação não deve criar uma nova regra de negócio.

Quando uma situação puder possuir mais de uma interpretação válida, a regra deve ser definida antes de sua implementação.

22. Fonte da verdade e documentação

Este documento, juntamente com os demais documentos funcionais aprovados em "docs/", constitui a fonte de verdade das regras de negócio do Escalar.

Este documento define princípios e regras transversais. As regras detalhadas de cada domínio devem permanecer nos documentos específicos correspondentes.

Nenhuma implementação deve criar comportamento de negócio apenas por conveniência técnica.

23. Regra para agentes

Agentes utilizados no desenvolvimento do Escalar não devem criar regras de negócio ausentes da documentação.

Quando houver dúvida funcional, ambiguidade, contradição ou ausência de definição:

1. a questão deve ser identificada;
2. nenhuma interpretação deve ser transformada automaticamente em regra oficial;
3. a decisão deve ser tomada no processo de definição do produto;
4. somente depois a regra aprovada deve ser incorporada à documentação.

Decisões técnicas podem ser tomadas durante a implementação quando não alterarem o comportamento de negócio previamente definido.

«Princípio de preservação da decisão: uma decisão materializada não deve ser silenciosamente reescrita por uma alteração posterior de cadastro, modelo, lotação, ocorrência ou configuração.»