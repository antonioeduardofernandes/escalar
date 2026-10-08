# Escalar — Visão do Produto

**Status:** v0.1 — Em elaboração

## 1. Visão geral

O **Escalar** é um sistema de gestão de escalas hospitalares desenvolvido para organizar, controlar e acompanhar a jornada dos profissionais de enfermagem e demais servidores envolvidos na elaboração das escalas.

O sistema tem como objetivo substituir processos atualmente baseados em planilhas, arquivos compartilhados e controles manuais por uma plataforma centralizada, permitindo maior organização, rastreabilidade, segurança das informações e redução de erros.

O Escalar será concebido inicialmente para utilização no âmbito hospitalar, considerando a existência de múltiplos setores, diferentes categorias profissionais, gestores e diferentes níveis de acesso.

A proposta não é simplesmente reproduzir uma planilha em formato de sistema. O objetivo é criar uma ferramenta própria para **gestão de escalas**, capaz de aplicar as regras institucionais, auxiliar o gestor na elaboração da escala e manter histórico das alterações realizadas.

---

## 2. Objetivos

O Escalar deverá:

- centralizar as informações relacionadas às escalas;
- facilitar a elaboração das escalas mensais;
- reduzir erros decorrentes de controles manuais;
- permitir validações automáticas das regras de escala;
- facilitar a visualização da jornada individual e coletiva;
- permitir acompanhamento da carga horária;
- controlar diferentes tipos de plantão e jornadas;
- registrar alterações realizadas nas escalas;
- preservar histórico e rastreabilidade;
- controlar permissões conforme o papel de cada usuário;
- permitir o fechamento das escalas;
- possibilitar auditoria das alterações;
- fornecer informações e relatórios para gestores e setores responsáveis.

---

## 3. Abrangência

O sistema deverá ser preparado para atender a estrutura hospitalar como um todo, e não apenas um único setor.

A estrutura poderá possuir **mais de 12 setores**, cada um com suas próprias necessidades, profissionais, gestores e regras de dimensionamento.

O sistema deverá, portanto, separar claramente:

- instituição;
- setores;
- servidores;
- cargos;
- lotações;
- gestores;
- secretários;
- escalas;
- equipes/modelos;
- ocorrências e intercorrências.

---

## 4. Perfis e responsabilidades

O Escalar deverá possuir diferentes níveis de acesso.

### 4.1 Servidor

Usuário que consulta suas informações relacionadas à escala e, conforme as permissões institucionais, poderá visualizar:

- sua escala;
- seus plantões;
- sua carga horária;
- ocorrências relacionadas à sua jornada;
- informações pertinentes ao seu setor.

### 4.2 Gestor

O gestor será responsável pela administração da escala de um ou mais setores sob sua responsabilidade.

Poderá, conforme suas permissões:

- elaborar escalas;
- realizar alterações;
- consultar servidores;
- acompanhar carga horária;
- verificar conflitos;
- analisar alertas;
- fechar escalas.

O gestor deverá ser um profissional enfermeiro.

### 4.3 Secretário

O secretário atua como apoio administrativo do gestor.

Não é considerado gestor do setor.

Seu acesso poderá ser delegado pelo gestor, permitindo auxiliar na elaboração e manutenção das escalas dos setores aos quais possui acesso.

### 4.4 Divisão de Enfermagem

A Divisão de Enfermagem possuirá acesso ampliado ao sistema.

Deverá ser capaz de:

- consultar todos os setores;
- consultar todas as escalas;
- acompanhar alterações;
- acessar históricos;
- reabrir escalas fechadas quando necessário;
- autorizar ou realizar alterações excepcionais;
- acompanhar informações consolidadas.

---

## 5. Estrutura organizacional

Cada servidor deverá possuir **uma única lotação ativa por vez**.

A lotação determina o setor ao qual o servidor pertence naquele momento.

O sistema deverá permitir alterações de lotação, mantendo o histórico dessas alterações.

Um servidor poderá possuir diferentes vínculos ou características profissionais ao longo do tempo, mas o sistema deverá manter claramente identificada sua situação vigente.

---

## 6. Escalas

A escala será organizada principalmente de forma mensal.

Cada setor poderá possuir sua própria escala mensal, contendo os servidores pertencentes àquele setor e seus respectivos horários.

A escala deverá permitir diferentes modalidades de jornada, incluindo:

### Plantões

- **SD:** 07h às 19h — 12 horas;
- **SN:** 19h às 07h — 12 horas;
- **DN:** 07h às 07h do dia seguinte — 24 horas.

Para fins de contagem:

- SD = 1 plantão;
- SN = 1 plantão;
- DN = 2 plantões.

### Jornada diarista

Também deverão existir jornadas como:

- **M:** 07h às 13h;
- **T:** 13h às 19h;
- **MT:** jornada diurna configurável.

O sistema deverá permitir jornadas especiais autorizadas, como jornadas de 8 ou 10 horas, sem alterar as regras dos plantões padrão.

---

## 7. Carga horária

O sistema deverá calcular automaticamente as horas previstas na escala.

A referência ordinária de **120 horas mensais** será utilizada como parâmetro mínimo ordinário, não como limite máximo universal.

O sistema deverá permitir situações autorizadas de carga horária reduzida ou superior, evitando transformar a referência de 120 horas em uma regra rígida que impeça situações legítimas.

---

## 8. APH

O **APH** deverá ser tratado separadamente da escala ordinária.

Plantões de APH:

- possuem duração de 12 horas;
- são realizados de forma adicional;
- não compõem a carga horária ordinária mínima de 120 horas;
- devem permanecer registrados;
- devem aparecer nos registros e históricos correspondentes;
- não alteram a lotação do servidor.

O sistema deverá manter clara a diferença entre:

**escala ordinária × APH.**

---

## 9. Intercorrências

O Escalar deverá diferenciar a escala planejada daquilo que efetivamente ocorreu.

Uma escala representa o planejamento.

Posteriormente poderão ser registradas situações como:

- plantão realizado;
- falta justificada;
- falta injustificada;
- falta com compensação;
- férias;
- licença;
- afastamento;
- outras ocorrências institucionais.

Esses registros deverão permitir posteriormente a construção de um histórico da jornada efetivamente realizada.

---

## 10. Compensações

A ausência com compensação deverá gerar um débito de horas/plantões para o servidor.

A compensação posterior deverá ser registrada explicitamente.

A realização de um plantão posteriormente **não deverá ser interpretada automaticamente como compensação**.

O usuário deverá informar quando determinado plantão estiver sendo utilizado para quitar uma compensação.

APH não deverá ser utilizado automaticamente para compensação da jornada ordinária.

---

## 11. Dimensionamento

Cada setor poderá possuir parâmetros próprios de dimensionamento.

Esses parâmetros poderão estabelecer, por exemplo:

- quantidade mínima de profissionais;
- quantidade máxima;
- necessidade por período;
- necessidade por categoria;
- necessidade por turno.

O sistema deverá utilizar essas informações para gerar **alertas** ao gestor.

Um alerta de dimensionamento não deverá necessariamente impedir a elaboração da escala.

O gestor poderá prosseguir quando houver uma justificativa ou situação institucional que explique a exceção.

Quando aplicável, essa decisão deverá permanecer registrada para fins de rastreabilidade.

---

## 12. Fechamento da escala

Após a conclusão da escala mensal, o gestor poderá realizar seu fechamento.

Uma escala fechada deverá passar para um estado de consulta, impedindo alterações comuns.

Alterações posteriores deverão exigir uma ação autorizada.

A Divisão de Enfermagem poderá liberar/reabrir uma escala fechada quando necessário.

A abertura deverá ser registrada para fins de auditoria.

Após as alterações, a escala deverá poder ser novamente fechada.

---

## 13. Auditoria e rastreabilidade

O sistema deverá preservar histórico das principais alterações realizadas.

Sempre que relevante, deverá ser possível identificar:

- quem realizou a alteração;
- quando realizou;
- o que foi alterado;
- situação anterior;
- situação posterior;
- motivo ou justificativa, quando aplicável.

A rastreabilidade será um dos princípios fundamentais do Escalar.

---

## 14. Equipes e modelos

O sistema deverá permitir a criação de **modelos reutilizáveis de escala/equipe**.

Esses modelos serão específicos de cada setor e poderão ser utilizados como base para novas escalas mensais.

Uma alteração individual realizada na escala de determinado mês não deverá modificar automaticamente o modelo original.

Dessa forma, o modelo funciona como uma base reutilizável, enquanto a escala mensal representa uma aplicação concreta daquele modelo.

---

## 15. Escala planejada x escala realizada

O Escalar deverá manter uma separação conceitual entre:

**Planejamento**

> O que estava previsto na escala.

**Realização**

> O que efetivamente aconteceu.

Essa separação será importante para permitir posteriormente análises de faltas, compensações, alterações e demais intercorrências sem destruir a informação original da escala planejada.

---

## 16. Princípios do produto

O Escalar deverá seguir alguns princípios fundamentais:

### Simplicidade

A ferramenta deverá ser fácil de utilizar mesmo por usuários com diferentes níveis de familiaridade tecnológica.

### Clareza

As informações deverão ser apresentadas de maneira objetiva, evitando excesso de elementos visuais.

### Rastreabilidade

Alterações importantes deverão poder ser identificadas posteriormente.

### Segurança

Cada usuário deverá visualizar e alterar somente aquilo que seu perfil permitir.

### Flexibilidade

O sistema deverá acomodar diferentes realidades dos setores hospitalares sem transformar exceções em regras gerais.

### Não destruição do histórico

Alterações posteriores não deverão apagar informações importantes sobre o estado anterior da escala.

### Regras institucionais acima da automação

O sistema deverá auxiliar o gestor, e não substituir sua responsabilidade administrativa.

Alertas e validações deverão apoiar a tomada de decisão, salvo regras explicitamente definidas como bloqueantes.

---

## 17. Interface

A interface deverá ser:

- moderna;
- rápida;
- intuitiva;
- responsiva;
- adequada para computadores e tablets;
- confortável para utilização por toque;
- organizada para grandes volumes de informação.

O sistema **não deverá simplesmente reproduzir a experiência de uma planilha**.

As cores deverão ser utilizadas principalmente como elementos de informação e estado, e não apenas como decoração.

---

## 18. Evolução futura

O Escalar deverá ser desenvolvido de maneira modular, permitindo a inclusão futura de funcionalidades que não fazem parte do MVP.

Entre elas está a **Conferência da Escala**, destinada ao acompanhamento operacional da escala e registro de observações.

Essa funcionalidade deverá permanecer conceitualmente separada da escala oficial e das intercorrências administrativas.

Outros módulos poderão ser incorporados posteriormente conforme as necessidades institucionais forem identificadas.

---

## 19. Regra fundamental do projeto

O Escalar deverá ser desenvolvido de maneira **orientada às regras de negócio documentadas**.

As decisões sobre o funcionamento do sistema deverão ser definidas antes da implementação das respectivas funcionalidades.

O agente de programação deverá implementar as regras documentadas, **não criar novas regras de negócio por conta própria**.

Quando uma informação necessária para uma implementação não estiver definida na documentação, a decisão deverá retornar ao responsável pelo produto antes da implementação.

**O sistema pode sugerir, alertar e automatizar. A decisão sobre a regra institucional pertence ao projeto, não ao agente.**
