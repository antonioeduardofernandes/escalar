Escalar — Cadastros e Lotações

1. Unidade

O Escalar atende o hospital como um todo.

Unidade é o termo oficial utilizado no domínio e na interface do sistema para representar uma subdivisão organizacional do hospital.

Cada unidade pode possuir sua própria escala e configurações operacionais, conforme os módulos do sistema.

As unidades são entidades estruturadas, não campos de texto livre. Podem ser criadas, editadas e desativadas por usuários autorizados.

A desativação de uma unidade não deve apagar seu histórico nem modificar silenciosamente escalas existentes.

O termo “setor” não deve ser utilizado como nome oficial da entidade organizacional na interface, no glossário ou nos documentos de domínio do Escalar.

As unidades devem possuir informações suficientes para identificação e operação, conforme as necessidades dos módulos que as utilizam. Campos adicionais e uma eventual estrutura hierárquica devem ser definidos antes de sua implementação, caso sejam necessários.

2. Servidor

O cadastro de servidor é uma funcionalidade operacional de apoio à gestão de escalas. Não constitui um módulo integral de gestão de pessoas.

O registro representa uma entidade funcional identificada por uma matrícula institucional. O Escalar não mantém uma identidade permanente da pessoa física ao longo de diferentes matrículas.

O cadastro deve ser organizado em dados de identificação operacional e dados funcionais.

2.1. Dados de identificação

Os campos de identificação são:

- Matrícula: obrigatória, única e imutável após a criação.
- Nome: obrigatório.
- E-mail: obrigatório.
- Situação: ativo ou inativo.

CPF e data de nascimento não fazem parte do cadastro e não devem ser coletados nem armazenados.

Não existe campo de nome social.

2.2. Dados funcionais

Os dados funcionais são:

- Cargo: obrigatório, selecionado de uma lista administrável.
- Vínculo institucional: obrigatório, selecionado de uma lista administrável.
- Lotação principal: unidade à qual o servidor está operacionalmente vinculado, com vigência e histórico.

Não existem no cadastro os conceitos de função, categoria profissional ou regime independente.

O cargo e o vínculo institucional são imutáveis após a criação do cadastro.

A lotação principal pode ser alterada por usuário autorizado, respeitando as regras de vigência e preservação do histórico.

3. Matrícula

A matrícula é a identificação única do servidor no Escalar.

Deve existir apenas um cadastro para cada matrícula. A matrícula não pode ser alterada dentro do mesmo cadastro após sua criação.

Uma nova matrícula representa uma nova entidade "Servidor", mesmo que a pessoa física já esteja representada por outro registro.

O Escalar não deve implementar conciliação de identidades entre matrículas diferentes nem unificar históricos de servidores com matrículas distintas.

A unicidade da matrícula deve ser verificada pelo sistema de forma consistente, inclusive no backend.

3.1. Correção de matrícula

A matrícula é imutável após a criação.

O procedimento para tratar um erro de digitação identificado depois da criação ainda deve ser definido, especialmente quando o registro já possuir escalas, ocorrências ou outros dados operacionais relacionados.

Até que exista uma regra aprovada, o agente não deve implementar mecanismos de alteração excepcional da matrícula nem apagar ou substituir registros relacionados para contornar a restrição.

4. Cargo

O cargo faz parte dos dados funcionais do servidor.

O cargo deve ser selecionado de uma lista administrável. Não será permitido informar livremente um nome de cargo no cadastro do servidor.

Somente o Administrador pode cadastrar, editar e desativar opções da lista de cargos.

O cargo selecionado em um cadastro de servidor é imutável após a criação.

Se uma opção de cargo for desativada, ela deve permanecer identificável nos registros históricos, mas não deve estar disponível para novos cadastros.

A desativação de um cargo não deve modificar automaticamente cadastros existentes nem reescrever escalas.

Não existe o conceito de função ou categoria profissional no cadastro do servidor.

5. Vínculo institucional

O vínculo institucional representa a relação funcional do servidor com a instituição e constitui o campo utilizado para identificar essa relação no Escalar.

O vínculo é obrigatório, deve ser selecionado de uma lista administrável e é imutável após a criação do cadastro.

As opções podem incluir:

- Estatutário;
- Fiotec;
- Estado;
- contrato temporário identificado pelo respectivo certame, como 6º, 7º ou 8º certame.

A lista de opções deve ser administrada pelo Administrador. Novas opções, incluindo novos certames, devem poder ser cadastradas sem necessidade de alterar o código da aplicação.

Quando um vínculo corresponder a um contrato temporário vinculado a um certame, a identificação desse certame deve ser preservada de forma estruturada e clara.

Somente o Administrador pode cadastrar, editar ou desativar opções de vínculo institucional.

A desativação de uma opção de vínculo deve preservar sua identificação nos registros históricos e impedir sua seleção em novos cadastros, conforme aplicável.

A desativação de uma opção não deve alterar automaticamente servidores já cadastrados.

5.1. Ausência de campo regime

O Escalar não terá um campo independente de regime.

O vínculo institucional é o dado utilizado para identificar a relação funcional definida para o cadastro. Não deve existir outro campo destinado a duplicar essa informação sob o nome “regime”.

A organização operacional das jornadas, incluindo a aplicação de modelos de diaristas e plantonistas, deve ser tratada nas regras específicas de equipes, modelos e escalas, sem introduzir um campo de regime no cadastro do servidor.

6. Lotação principal

A lotação representa a vinculação operacional principal do servidor a uma unidade.

Cada servidor deve possuir uma única lotação principal vigente por vez.

A lotação deve manter histórico suficiente para identificar:

- o servidor;
- a unidade;
- o início da vigência;
- o fim da vigência, quando houver;
- o responsável pela alteração;
- as informações necessárias à rastreabilidade.

A alteração da lotação encerra o período anterior e inicia o novo período, sem sobreposição de vigências.

Uma transferência deve preservar a informação de onde o servidor esteve anteriormente lotado.

O procedimento de alteração da lotação deve ser realizado por usuário autorizado, respeitando o âmbito de atuação e as permissões aplicáveis. A manutenção do cadastro de servidor e de sua lotação não constitui autorização para alterar escalas fora do âmbito permitido.

6.1. Relação entre lotação e escala

A lotação deve ser considerada nas regras de alocação e validação da escala.

Uma alocação incompatível com as regras de lotação deve ser identificada e impedida quando constituir violação de uma regra obrigatória.

A atuação excepcional em outra unidade pode ocorrer por APH quando se enquadrar nas regras específicas dessa modalidade.

APH não altera, por si só, a lotação principal.

As regras detalhadas de alocação, exceções e APH devem permanecer nos documentos específicos de escalas, plantões e intercorrências.

6.2. Alterações de lotação e escalas existentes

Uma mudança de lotação não pode apagar, substituir ou modificar silenciosamente turnos existentes.

O sistema deve identificar e sinalizar escalas, servidores, datas ou turnos potencialmente afetados para revisão por usuário autorizado.

Em escalas materializadas ou fechadas, a versão oficial e o histórico devem permanecer preservados. Qualquer alteração posterior deve respeitar o estado da escala e o fluxo de reabertura aplicável.

7. Permissões para manutenção do cadastro

Somente Administrador e Supervisor podem criar, editar, desativar ou reativar cadastros de servidores.

O Administrador atua conforme as permissões administrativas previstas.

O Supervisor atua dentro de seu âmbito de atuação autorizado.

O Gestor não pode criar, editar, desativar ou reativar servidores, mesmo que esses servidores participem das escalas sob sua responsabilidade.

O Servidor não pode editar o próprio cadastro.

A autorização deve ser verificada no backend. Ocultar ações na interface não substitui o controle efetivo de permissões.

7.1. Alterações permitidas

Os dados que podem ser alterados devem respeitar as regras específicas de cada campo:

- nome e e-mail podem ser atualizados por usuário autorizado, preservando a rastreabilidade;
- lotação principal pode ser alterada com vigência e histórico;
- situação ativa ou inativa pode ser alterada por usuário autorizado;
- matrícula, cargo e vínculo institucional não podem ser alterados após a criação.

As alterações permitidas não devem criar registros duplicados nem apagar informações necessárias para compreender o histórico do servidor.

7.2. Correção de dados imutáveis

Matrícula, cargo e vínculo institucional são imutáveis após a criação do cadastro.

O procedimento operacional para corrigir um erro nesses campos ainda deve ser definido, considerando se o registro já possui dados operacionais associados.

Até que a regra seja aprovada, o agente não deve implementar exceções que permitam alterar esses campos, transferir silenciosamente os dados para outro cadastro ou apagar históricos relacionados.

8. Inativação

O servidor possui uma situação de ativo ou inativo.

A inativação:

- bloqueia o acesso do servidor ao sistema;
- impede novas alocações;
- preserva o cadastro;
- preserva escalas, ocorrências, compensações e registros históricos;
- sinaliza escalas em elaboração que possam ter sido afetadas;
- não cancela nem remove silenciosamente plantões existentes.

A inativação não equivale a uma falta, licença ou outra ocorrência operacional.

Escalas materializadas ou fechadas devem permanecer preservadas. O tratamento de eventuais plantões futuros existentes no momento da inativação deve respeitar as regras de revisão e alteração de escalas, sem remoção automática.

A inativação deve ser registrada conforme as regras de auditoria.

9. Reativação

A reativação pode ser realizada por Administrador ou Supervisor autorizado.

A reativação restabelece a possibilidade de utilização do servidor nas operações permitidas, respeitando as permissões, a lotação e as demais regras vigentes.

A reativação:

- preserva o histórico anterior;
- não duplica o cadastro;
- não recria vínculos históricos;
- não reinsere automaticamente o servidor em escalas anteriores;
- não altera escalas materializadas ou fechadas.

A reativação deve ser registrada conforme as regras de auditoria.

10. E-mail e acesso individual

O e-mail é um dado obrigatório do cadastro e pode ser utilizado para ativação da conta, recuperação de acesso, notificações e consulta individual da escala.

O processo de acesso deve respeitar os seguintes princípios:

- a conta é criada ou habilitada por usuário autorizado;
- o sistema envia um link seguro de ativação;
- o próprio servidor define sua senha;
- senhas não devem ser enviadas por e-mail;
- links de ativação e recuperação devem ter validade limitada e uso único;
- a recuperação de senha não deve revelar se um endereço de e-mail está cadastrado;
- o acesso individual deve exigir autenticação ou mecanismo seguro aprovado;
- o servidor só pode consultar a própria escala.

O mecanismo técnico de autenticação, a política de sessão e os parâmetros de segurança serão definidos na arquitetura técnica.

11. Histórico e rastreabilidade

Alterações relevantes no cadastro e na lotação devem preservar informações suficientes para compreender os estados anteriores.

O histórico deve permitir distinguir, conforme aplicável:

- situação anterior e posterior;
- campo alterado;
- responsável pela alteração;
- data e hora;
- período de vigência;
- unidade anterior e nova unidade;
- ativação e inativação;
- reativação;
- relações operacionais afetadas.

A alteração de dados atuais não deve apagar informações necessárias para interpretar registros históricos.

O formato técnico do histórico, os eventos auditados e a política de retenção serão definidos em "09-fechamento-e-auditoria.md".

12. Relação com escalas materializadas e fechadas

Alterações posteriores no cadastro do servidor ou na lotação não devem reescrever silenciosamente escalas materializadas ou fechadas.

Quando uma alteração cadastral tiver efeito futuro, ela deve respeitar a vigência aplicável.

O sistema deve identificar e sinalizar escalas potencialmente afetadas para revisão por usuário autorizado.

A escala materializada permanece como registro do planejamento definido para o período correspondente.

Escalas fechadas devem permanecer protegidas contra alterações operacionais comuns. Mudanças posteriores devem respeitar as regras de reabertura, revisão, nova validação, fechamento e publicação.

13. Regras para implementação

O cadastro deve representar os conceitos de servidor, cargo, vínculo institucional, unidade e lotação de forma estruturada.

O agente de desenvolvimento não deve:

- adicionar CPF ou data de nascimento ao cadastro;
- criar campos de nome social, função, categoria profissional ou regime independente;
- permitir cargo ou vínculo institucional como texto livre;
- permitir a alteração de matrícula, cargo ou vínculo após a criação;
- conceder ao Gestor permissões para manter cadastros de servidores;
- criar novos tipos de vínculo sem manutenção administrativa autorizada;
- criar exceções para campos imutáveis sem decisão explícita;
- modificar retroativamente escalas materializadas em razão de alterações cadastrais;
- apagar histórico para simplificar a implementação;
- tratar a desativação de um servidor como cancelamento automático de plantões;
- tratar a reativação como reinserção automática em escalas anteriores;
- usar o termo “setor” como nome oficial da entidade organizacional na interface.

Quando houver dúvida sobre a estrutura ou o comportamento de um cadastro, a decisão deve ser definida antes da implementação.

14. Pendências de definição

As seguintes questões devem ser decididas antes da implementação dos comportamentos correspondentes:

- procedimento para corrigir uma matrícula digitada incorretamente após a criação;
- procedimento para corrigir cargo ou vínculo institucional incorreto quando o cadastro já possuir registros operacionais;
- estrutura hierárquica de unidades, caso seja necessária;
- regras específicas para tratar transferências em relação a escalas futuras;
- detalhes técnicos de histórico e auditoria;
- parâmetros técnicos de autenticação, sessão e recuperação de acesso.

Essas pendências não autorizam a criação de comportamentos provisórios que contrariem as regras já aprovadas. Devem ser registradas e submetidas à definição do produto antes da implementação das funcionalidades correspondentes.