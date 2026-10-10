# Índice da Documentação do Escalar

## 1. Finalidade

Este documento cataloga a documentação do projeto Escalar, indicando a localização, a finalidade e as relações entre os arquivos.

Seu objetivo é facilitar a consulta, reduzir a duplicação de conteúdo e permitir que pessoas e agentes de desenvolvimento localizem as fontes pertinentes a cada tarefa.

O índice deve ser atualizado sempre que documentos forem criados, removidos, renomeados ou movidos, ou quando sua finalidade mudar de maneira relevante.

## 2. Repositório oficial

* **Repositório:** https://github.com/antonioeduardofernandes/escalar
* **Branch principal:** `main`
* **Padrão dos links RAW:** `https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/CAMINHO_DO_ARQUIVO`

Os links deste índice pressupõem que os arquivos estejam publicados na branch `main`. A existência e a validade dos caminhos devem ser verificadas antes da publicação.

## 3. Documentos de entrada e gestão

| Documento              | Caminho                                                                                                                                                                          | Finalidade                                         |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| README                 | [`README.md`](../README.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/README.md)                                                            | Apresentação do projeto e navegação inicial.       |
| Estado do projeto      | [`gestao/ESTADO_DO_PROJETO.md`](ESTADO_DO_PROJETO.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/gestao/ESTADO_DO_PROJETO.md)                | Situação atual, pendências, riscos e próxima ação. |
| Índice documental      | [`gestao/INDICE_DOCUMENTACAO.md`](INDICE_DOCUMENTACAO.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/gestao/INDICE_DOCUMENTACAO.md)          | Catálogo e navegação pela documentação.            |
| Decisões arquiteturais | [`gestao/DECISOES_ARQUITETURAIS.md`](DECISOES_ARQUITETURAIS.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/gestao/DECISOES_ARQUITETURAIS.md) | Registro rastreável das decisões arquiteturais.    |

## 4. Documentação de especificação

A documentação funcional e técnica fica na pasta `docs/`.

| Documento                           | Caminho relativo                                                                                                                                                                                                      | Finalidade principal                                                   |
| ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| 01 — Visão do produto               | [`docs/01-visao-do-produto.md`](../docs/01-visao-do-produto.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/01-visao-do-produto.md)                                           | Visão geral, objetivos e escopo do produto.                            |
| 02 — Regras de negócio              | [`docs/02-regras-de-negocio.md`](../docs/02-regras-de-negocio.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/02-regras-de-negocio.md)                                        | Regras que determinam o comportamento esperado do sistema.             |
| 03 — Permissões e papéis            | [`docs/03-permissoes-e-papeis.md`](../docs/03-permissoes-e-papeis.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/03-permissoes-e-papeis.md)                                  | Papéis, responsabilidades e permissões.                                |
| 04 — Cadastros e lotações           | [`docs/04-cadastros-e-lotacoes.md`](../docs/04-cadastros-e-lotacoes.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/04-cadastros-e-lotacoes.md)                               | Requisitos cadastrais e informações funcionais.                        |
| 05 — Escalas e plantões             | [`docs/05-escalas-e-plantoes.md`](../docs/05-escalas-e-plantoes.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/05-escalas-e-plantoes.md)                                     | Regras e requisitos de escalas e plantões.                             |
| 06 — Equipes e modelos              | [`docs/06-equipes-e-modelos.md`](../docs/06-equipes-e-modelos.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/06-equipes-e-modelos.md)                                        | Conceitos e regras relacionados a equipes e modelos.                   |
| 07 — Intercorrências e compensações | [`docs/07-intercorrencias-e-compensacoes.md`](../docs/07-intercorrencias-e-compensacoes.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/07-intercorrencias-e-compensacoes.md) | Tratamento de intercorrências e compensações.                          |
| 08 — Dimensionamento                | [`docs/08-dimensionamento.md`](../docs/08-dimensionamento.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/08-dimensionamento.md)                                              | Critérios e requisitos de dimensionamento.                             |
| 09 — Fechamento e auditoria         | [`docs/09-fechamento-e-auditoria.md`](../docs/09-fechamento-e-auditoria.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/09-fechamento-e-auditoria.md)                         | Fechamento, responsabilidade operacional, auditoria e rastreabilidade. |
| 10 — Relatórios                     | [`docs/10-relatorios.md`](../docs/10-relatorios.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/10-relatorios.md)                                                             | Requisitos e conceitos relativos a relatórios.                         |
| 11 — Arquitetura técnica            | [`docs/11-arquitetura-tecnica.md`](../docs/11-arquitetura-tecnica.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/11-arquitetura-tecnica.md)                                  | Arquitetura e orientações técnicas do sistema.                         |
| 12 — Interface e experiência        | [`docs/12-interface-e-experiencia.md`](../docs/12-interface-e-experiencia.md) · [RAW](https://raw.githubusercontent.com/antonioeduardofernandes/escalar/main/docs/12-interface-e-experiencia.md)                      | Interface, experiência de uso e fluxos de interação.                   |

## 5. Documentação de possibilidades futuras

* [`docs/99-futuro/`](../docs/99-futuro/): diretório reservado à documentação relacionada a possibilidades futuras.

Os arquivos individuais desse diretório devem ser catalogados nesta seção quando seus nomes, conteúdos e finalidades forem verificados.

## 6. Relações entre os documentos

A documentação deve ser consultada conforme o tipo de trabalho:

* **Requisitos e escopo:** visão do produto e regras de negócio.
* **Cadastros:** regras de negócio, cadastros e lotações.
* **Autorização de acesso:** permissões e papéis, em conjunto com os requisitos da funcionalidade.
* **Escalas e plantões:** regras de negócio, escalas, modelos, intercorrências e dimensionamento, conforme aplicável.
* **Fechamento e auditoria:** regras de negócio, permissões, escalas e documento de fechamento e auditoria.
* **Arquitetura e implementação:** arquitetura técnica e os requisitos funcionais envolvidos.
* **Interface:** interface e experiência, regras de negócio e permissões aplicáveis.
* **Continuidade do trabalho:** estado do projeto, índice documental e registro de decisões arquiteturais.

O índice orienta a consulta, mas não substitui o conteúdo normativo dos documentos de especificação.

## 7. Manutenção do índice

Quando um documento for alterado estruturalmente:

1. Confirmar o caminho e o nome do arquivo.
2. Atualizar os links relativos.
3. Atualizar o link RAW da branch `main`.
4. Revisar a descrição e as relações com outros documentos.
5. Verificar se o README precisa ser atualizado.

Não registrar como existente um arquivo que ainda não foi criado ou publicado. Caso um caminho esteja planejado, identificá-lo explicitamente como pendente até sua confirmação.
