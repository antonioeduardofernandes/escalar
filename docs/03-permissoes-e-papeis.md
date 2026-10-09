Escalar — Permissões e Papéis

1. Princípio geral

O Escalar possui exatamente quatro papéis de usuário:

- Administrador;
- Servidor;
- Gestor;
- Supervisor.

As permissões devem ser definidas por três dimensões principais:

- Papel: o que o usuário pode fazer.
- Âmbito de atuação: em quais unidades o usuário pode executar suas ações.
- Estado do recurso: quais operações são permitidas considerando o estado da escala ou do cadastro.

Uma autorização específica pode restringir ou complementar uma operação somente quando estiver prevista nas regras aprovadas.

O sistema não deve assumir que todo usuário possui acesso global.

A interface pode ocultar opções não autorizadas, mas a autorização efetiva deve ser verificada no backend. A ocultação de um botão ou item de menu não constitui mecanismo de segurança suficiente.

2. Administrador

O Administrador é responsável pela manutenção administrativa e estrutural do sistema.

Pode, conforme os módulos administrativos previstos:

- criar, editar e desativar unidades;
- cadastrar, editar, desativar e reativar usuários;
- administrar os papéis e as permissões;
- cadastrar, editar e desativar cargos;
- cadastrar, editar e desativar opções de vínculo institucional;
- manter configurações administrativas;
- cadastrar, editar e desativar tipos e códigos de licença;
- executar as demais operações de configuração explicitamente autorizadas.

O Administrador também pode criar, editar, desativar e reativar cadastros de servidores, respeitando as regras de imutabilidade e histórico.

O Administrador não recebe automaticamente permissões operacionais de elaboração, materialização, fechamento ou reabertura de escalas apenas por possuir o papel administrativo.

A manutenção administrativa de usuários e permissões não deve permitir que o Administrador amplie indevidamente seu próprio acesso operacional.

3. Servidor

O Servidor possui acesso individual às informações disponibilizadas para sua consulta.

Pode:

- autenticar-se no sistema;
- consultar a própria escala publicada;
- consultar as informações disponibilizadas para sua visualização;
- baixar, opcionalmente, o PDF da própria escala, quando disponível;
- encerrar sua sessão;
- solicitar recuperação de acesso pelos mecanismos seguros do sistema.

Não pode:

- consultar escalas individuais de outros servidores sem autorização específica prevista;
- elaborar, editar, materializar, fechar ou reabrir escalas;
- alterar o próprio cadastro;
- alterar cargos ou vínculos institucionais;
- acessar módulos administrativos;
- consultar informações restritas de outros usuários.

O acesso individual deve ser verificado no backend. Conhecer ou receber o endereço de uma página não pode conceder acesso à escala de outra pessoa.

4. Gestor

O Gestor atua nas unidades atribuídas ao seu âmbito de atuação.

Pode:

- consultar e elaborar escalas abertas;
- aplicar modelos de escala às equipes;
- ajustar turnos e registrar exceções permitidas;
- consultar e comparar o mês anterior como referência;
- gerar propostas de preenchimento e analisar suas prévias;
- executar validações e revisar pendências;
- configurar equipes e modelos dentro das permissões autorizadas;
- prorrogar a vigência de aplicação de modelos conforme as regras;
- definir o dimensionamento da cobertura;
- registrar ocorrências;
- classificar faltas como compensáveis ou não compensáveis;
- acompanhar dívidas e quitações de compensação;
- materializar e fechar escalas dentro do seu âmbito;
- consultar relatórios autorizados;
- revisar impactos de mudanças que afetem escalas abertas.

O Gestor não pode:

- criar, editar, desativar ou reativar cadastros de servidores;
- administrar cargos ou opções de vínculo institucional;
- reabrir escalas fechadas;
- alterar escalas fora do seu âmbito de atuação;
- contornar bloqueios obrigatórios de validação;
- substituir turnos existentes por geração automática sem prévia, revisão e confirmação explícita.

A edição de uma escala depende de seu estado e das regras operacionais aplicáveis.

5. Supervisor

O Supervisor possui responsabilidades operacionais ampliadas dentro do seu âmbito de atuação.

Pode:

- consultar e elaborar escalas;
- executar os ajustes operacionais permitidos;
- gerar propostas e revisar prévias;
- executar validações e revisar pendências;
- configurar equipes e modelos dentro das permissões autorizadas;
- prorrogar a vigência de aplicação de modelos conforme as regras;
- definir ou ajustar dimensionamento dentro do âmbito autorizado;
- registrar ocorrências;
- classificar faltas como compensáveis ou não compensáveis;
- materializar e fechar escalas;
- reabrir escalas fechadas, mediante justificativa obrigatória e registro de auditoria;
- consultar relatórios autorizados;
- cadastrar datas institucionais adicionais e pontos facultativos;
- criar, editar, desativar e reativar cadastros de servidores dentro do âmbito permitido;
- corrigir dados cadastrais que possam ser alterados conforme as regras;
- revisar impactos de mudanças cadastrais, operacionais e de calendário sobre as escalas.

A permissão para reabrir uma escala não elimina a necessidade de registrar o motivo, preservar a versão anterior e executar novamente as etapas de validação, materialização e fechamento aplicáveis.

O Supervisor não deve ser considerado automaticamente autorizado a atuar em todas as unidades. Seu acesso deve respeitar o âmbito de atuação configurado.

6. Unidade organizacional e Divisão de Enfermagem

Unidade é a entidade organizacional utilizada pelo Escalar para delimitar estruturas e âmbitos operacionais.

A Divisão de Enfermagem pode existir como uma unidade organizacional do hospital. Não constitui um papel adicional no sistema.

Usuários vinculados à Divisão de Enfermagem devem receber um dos quatro papéis existentes e as permissões correspondentes.

A vinculação organizacional à Divisão de Enfermagem não concede automaticamente permissões de Administrador, Gestor ou Supervisor.

Não existe um papel denominado “Divisão de Enfermagem” com permissões implícitas de acesso global ou reabertura de escalas.

7. Âmbito de atuação

O papel define o que o usuário pode fazer. O âmbito define onde ele pode fazer.

Exemplo conceitual:

«Um usuário com papel Gestor pode ter permissão para operar escalas, mas somente nas unidades para as quais possui autorização.»

O sistema deve filtrar os dados apresentados de acordo com as unidades autorizadas.

A seleção de uma unidade na interface não amplia as permissões do usuário.

O backend deve verificar o papel, a unidade, o estado do recurso e a operação solicitada em cada ação protegida.

A possibilidade de um usuário possuir múltiplos papéis simultaneamente não está definida neste documento e não deve ser presumida na implementação. A arquitetura de autorização deve respeitar essa pendência até que haja decisão explícita.

8. Cadastro e manutenção de servidores

Somente Administrador e Supervisor podem criar, editar, desativar ou reativar servidores.

O Administrador atua conforme suas permissões administrativas. O Supervisor atua dentro de seu âmbito autorizado.

O Gestor não pode realizar essas operações, mesmo quando administra escalas que utilizam os servidores cadastrados.

O Servidor não pode editar o próprio cadastro.

As operações de manutenção devem respeitar as seguintes regras:

- matrícula é obrigatória, única e imutável;
- cargo e vínculo institucional são obrigatórios e imutáveis após a criação;
- cargos e vínculos são selecionados de listas administráveis;
- somente Administrador pode manter as listas de cargos e vínculos;
- CPF e data de nascimento não são coletados nem armazenados;
- alterações permitidas devem preservar a rastreabilidade;
- desativação não apaga histórico nem cancela silenciosamente plantões existentes;
- reativação não reinclui automaticamente o servidor em escalas anteriores.

A lotação deve respeitar as regras de vigência e histórico definidas em "04-cadastros-e-lotacoes.md".

9. Equipes, modelos e dimensionamento

Gestor e Supervisor podem administrar equipes, modelos e dimensionamento dentro de seus respectivos âmbitos, respeitando as regras específicas de cada módulo.

A aplicação de modelos deve apresentar prévia obrigatória antes de alterar a matriz.

Por padrão, a geração preenche células vazias e preserva células já preenchidas. A substituição exige prévia, revisão e confirmação explícita.

Alterações em equipes, modelos ou vigências não podem modificar silenciosamente escalas existentes.

10. Escalas e estados operacionais

As permissões de operação dependem do estado da escala.

10.1. Escala em elaboração

Gestor e Supervisor podem editar escalas dentro de seus respectivos âmbitos.

O sistema deve validar alterações relevantes, indicar conflitos e pendências e preservar alterações ainda não confirmadas pelo backend.

10.2. Escala materializada

A escala materializada representa uma versão registrada do planejamento.

Gestor e Supervisor podem realizar as operações de fechamento autorizadas. Alterações que exijam revisão devem respeitar o fluxo de reabertura quando aplicável.

A materialização não equivale a fechamento nem a publicação.

10.3. Escala fechada

Uma escala fechada não pode ser alterada como se estivesse em elaboração.

Somente Supervisor pode reabrir a escala. A reabertura exige justificativa e registro de auditoria.

Após a reabertura, a versão anterior permanece preservada. A versão revisada deve ser validada novamente e passar pelas etapas necessárias antes de um novo fechamento e publicação.

10.4. Fechamento e publicação

Gestor e Supervisor podem fechar escalas dentro do seu âmbito.

O fechamento exige confirmação explícita e validação atualizada no backend.

Após o fechamento, o sistema inicia a notificação dos servidores afetados. A falha no envio de e-mail não desfaz o fechamento.

11. Ocorrências e compensações

Gestor e Supervisor podem registrar ocorrências dentro de seu âmbito, conforme as regras do módulo.

A classificação de uma falta como compensável ou não compensável é uma decisão operacional do Gestor ou Supervisor autorizado.

Somente faltas classificadas como compensáveis geram dívida de horas.

A quitação deve ser registrada explicitamente e respeitar as regras de jornadas completas. O sistema não deve quitar dívidas automaticamente por inclusão de plantões futuros ou por APH.

12. Relatórios e consulta

Cada usuário só pode acessar relatórios e dados compatíveis com seu papel e âmbito de atuação.

O Gestor e o Supervisor podem consultar os relatórios operacionais autorizados para suas unidades.

O Administrador pode consultar informações administrativas necessárias às suas atribuições, sem receber automaticamente permissões operacionais para alterar escalas.

O Servidor pode consultar a própria escala e as informações autorizadas para sua visualização.

13. Princípio de menor privilégio

Um usuário deve possuir somente as permissões necessárias para exercer suas responsabilidades.

Não se deve conceder acesso administrativo apenas para permitir que uma operação específica seja executada.

A interface deve apresentar apenas as opções pertinentes ao papel, mas o backend deve ser a autoridade final sobre permissões.

14. Auditoria das operações

As operações relevantes devem ser rastreáveis conforme o domínio e as regras de auditoria.

Devem ser preservados, quando aplicáveis:

- responsável pela ação;
- data e hora;
- unidade e recurso afetados;
- estado anterior e posterior;
- motivo da reabertura;
- versão da escala;
- resultado de validação;
- alterações cadastrais e de lotação;
- operações de materialização, fechamento e publicação.

Os detalhes técnicos do registro e a política de retenção serão definidos na etapa de arquitetura e documentados em "09-fechamento-e-auditoria.md".

15. Regra para implementação

O agente de desenvolvimento não deve:

- criar novos papéis sem aprovação;
- tratar uma unidade organizacional como papel;
- ampliar permissões por conveniência técnica;
- transformar um usuário operacional em Administrador para contornar restrições;
- assumir acesso global quando o âmbito não estiver definido;
- permitir ao Gestor manter cadastros de servidores;
- permitir ao Administrador reabrir escalas apenas por possuir papel administrativo;
- criar regras de delegação não documentadas;
- considerar a ocultação de elementos da interface como controle suficiente de segurança.

Quando uma permissão necessária não estiver definida, a lacuna deve ser registrada e submetida à definição do produto antes da implementação da operação correspondente.