# Estado do Projeto Escalar

## 1. Finalidade deste documento

Este documento registra o estado atual do projeto Escalar para permitir a continuidade organizada do planejamento, da documentação e do desenvolvimento entre sessões de trabalho.

Deve funcionar como ponto de partida para retomar o projeto sem depender exclusivamente do histórico de conversas.

O documento deve ser atualizado sempre que houver progresso relevante, mudança de prioridade, resolução de pendência, identificação de risco ou definição de uma nova próxima ação.

## 2. Identificação do projeto

* **Nome:** Escalar
* **Objetivo:** desenvolver um sistema de gestão de escalas hospitalares.
* **Repositório oficial:** https://github.com/antonioeduardofernandes/escalar
* **Branch principal:** `main`
* **Fonte oficial do código e da documentação:** GitHub.

## 3. Organização documental

A organização documental planejada separa duas finalidades.

### 3.1. Especificação do sistema

A pasta `docs/` contém a documentação funcional e técnica utilizada para definir o comportamento esperado do sistema e orientar sua implementação.

Os documentos existentes abrangem visão do produto, regras de negócio, permissões, cadastros, escalas, modelos, intercorrências, dimensionamento, fechamento, relatórios, arquitetura técnica e interface.

A pasta `docs/99-futuro/` reúne documentação relacionada a possibilidades futuras.

### 3.2. Gestão e continuidade

A pasta `gestao/` reúne os documentos utilizados para acompanhar o trabalho e preservar o contexto entre sessões:

* `ESTADO_DO_PROJETO.md`: situação atual, pendências, riscos e próxima ação.
* `INDICE_DOCUMENTACAO.md`: catálogo e navegação documental.
* `DECISOES_ARQUITETURAIS.md`: registro de decisões arquiteturais.

O `README.md`, localizado na raiz, funciona como porta de entrada do repositório.

**Nota:** a estrutura acima representa a organização planejada. A existência e a localização de cada arquivo devem ser confirmadas no repositório.

## 4. Diretrizes confirmadas do projeto

### Cadastro de servidores

* A matrícula é o identificador único do servidor e é obrigatória.
* Nome, vínculo institucional e cargo são obrigatórios.
* E-mail é opcional.
* Não deve existir CPF ou data de nascimento no cadastro.
* Não haverá nome social.
* Não deve existir campo separado de função nem de categoria profissional.

### Vínculos institucionais

Os vínculos previstos são:

* Ministério da Saúde.
* Fiotec.
* Contrato temporário, com identificação do número do certame.

### Modelos

Não existe uma entidade independente de equipes. O conceito relevante é o de modelos. Os termos “equipe” e “modelo” não devem ser tratados como sinônimos indiscriminadamente; o significado deve ser avaliado conforme o contexto.

### Responsabilidade pelo fechamento das escalas

A responsabilidade operacional pelo conteúdo da escala fechada pertence ao gestor que realiza sua finalização e fechamento, independentemente de quem executou tecnicamente as operações preparatórias.

Os registros técnicos servem à integridade, ao diagnóstico, à rastreabilidade e ao reprocessamento. A execução técnica não transfere a responsabilidade operacional.

## 5. Situação atual conhecida

### Fatos confirmados

* O repositório oficial do projeto é o GitHub indicado neste documento.
* A branch principal é `main`.
* A documentação do projeto está organizada na pasta `docs/`.
* Foram identificados doze documentos numerados de especificação, além da pasta `docs/99-futuro/`.
* Está sendo estabelecida uma separação entre documentação de especificação e documentação de gestão e continuidade.
* O trabalho de planejamento e análise ocorre em conjunto com o responsável pelo projeto; a implementação e os testes podem ser executados no ambiente local de desenvolvimento.

### Itens ainda não verificados

* A existência de todos os arquivos de controle na estrutura definitiva.
* A consistência integral dos documentos de especificação com as diretrizes confirmadas.
* O estágio real de implementação das funcionalidades.
* A existência, a cobertura e os resultados de testes automatizados.
* A correspondência entre todos os requisitos documentados e o código existente.

Não se deve considerar um requisito implementado apenas porque está documentado.

## 6. Pendências de organização e documentação

1. Criar e revisar os documentos de controle do projeto.
2. Confirmar a organização final das pastas e a validade dos links.
3. Revisar a documentação de especificação em busca de divergências com as diretrizes confirmadas.
4. Identificar eventuais decisões arquiteturais documentadas e distinguir decisões aprovadas de propostas.
5. Registrar o estágio de implementação com base em verificações efetivas, quando essa análise for realizada.

## 7. Riscos e cuidados

* Divergências entre regras de negócio confirmadas e documentos existentes.
* Perda de contexto entre conversas se o estado do projeto não for atualizado.
* Referências quebradas após movimentação de documentos.
* Confusão entre requisitos documentados e funcionalidades efetivamente implementadas.
* Registro de propostas técnicas como se fossem decisões aprovadas.
* Confusão entre responsabilidade operacional e execução técnica no fechamento das escalas.

## 8. Regras de atualização deste documento

Atualizar este documento quando houver:

* Conclusão de uma etapa relevante.
* Mudança na prioridade ou no escopo de trabalho.
* Resolução ou inclusão de pendências.
* Identificação de riscos relevantes.
* Decisão que altere a próxima ação recomendada.
* Mudança na organização do projeto que afete a continuidade.

O registro deve refletir a situação real, não apenas o plano pretendido.

## 9. Próxima ação recomendada

Concluir a organização dos documentos de controle, verificar os links e registrar a estrutura documental definitiva no GitHub.

Em seguida, revisar as especificações existentes e identificar divergências, priorizando as que afetem regras de negócio, cadastros, permissões, arquitetura ou fechamento das escalas.

## 10. Histórico de atualização

| Data        | Alteração                                          |
| ----------- | -------------------------------------------------- |
| A registrar | Criação inicial do documento de estado do projeto. |

A data e as atualizações futuras devem ser preenchidas de acordo com as alterações efetivamente realizadas.
