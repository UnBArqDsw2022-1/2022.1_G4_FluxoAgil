# Léxicos

## Histórico de versões

| Data     | Versão | Descrição            | Autor                                                                                     | Revisor                                |
| -------- | ------ | -------------------- | ----------------------------------------------------------------------------------------- | -------------------------------------- |
| 19/06/22 | 1.0    | Criação do documento | [Yudi Yamane](https://github.com/yudi-azvd), [Amanda Nobre](https://github.com/AmandaNbr) | [Lucas Braun](https://github.com/lbvx) |

## Introdução

Léxico é uma técnica de modelagem que tem como objeto principal a própria 
linguagem, pois busca descrever símbolos (palavras chave e frases recorrentes no
desenvolvimento do projeto) para mapeá-los e entender as noções e impactos de 
cada símbolo levantado.

A descrição de símbolos ocorre das 3 seguintes formas:

| Tipo   | Noção                                                                    | Impacto                                                                                                      |
| ------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| VERBO  | Quem realiza, quando acontece e quais os procedimentos envolvidos.       | Quais os reflexos da ação no ambiente (outras ações que devem ocorrer) e quais os novos estados decorrentes. |
| OBJETO | Definir o objeto e identificar outros objetos com os quais se relaciona. | Ações que podem ser aplicadas ao objeto.                                                                     |
| ESTADO | O que significa e quais ações levaram a esse estado.                     | Identificar outros estados e ações que podem ocorrer a partir do estado que se descreve.                     |


## Metodologia

Para definir os léxicos foi feita uma introspecção através da navegação nos 
artefatos e requisitos levantados e, a partir disso, os símbolos foram coletados. 
Os léxicos estão organizados por tipo, em ordem alfabética e seguindo o seguinte 
modelo:

| LXX       | Nome do Léxico            |
| --------- | ------------------------- |
| Tipo      | (Verbo, objeto ou estado) |
| Sinônimos | Sinônimos do léxico       |
| Noção     | Noção do léxico           |
| Impacto   | Impactos do léxico        |
| Autor     | Autor do léxico           |

## Participantes

- [Amanda Nobre](https://github.com/AmandaNbr)
- [Yudi Yamane](https://github.com/yudi-azvd)

## Resultados


### OBJETO

#### Léxico 01 - Usuário

| L01       | Usuário                                                     |
| --------- | ----------------------------------------------------------- |
| Tipo      | Objeto                                                      |
| Sinônimos | Aluno                                                       |
| Noção     | Indivíduo que pretende utilizar o sistema                   |
| Impacto   | O usuário envia o histórico acadêmico                       |
|           | O usuário pode visualizar o tempo de duração de um episódio |
|           | O usuário escolhe matérias específicas                      |
|           | O usuário recebe recomendação do fluxo ideal                |

#### Léxico 02 - Fluxo

| L02       | Fluxo                                                           |
| --------- | --------------------------------------------------------------- |
| Tipo      | Objeto                                                          |
| Sinônimos | -                                                               |
| Noção     | Caminho de matérias a serem seguidas recomendadas pelo software |
| Impacto   | O sistema recomenda um fluxo ideal                              |
|           | O usuário poderá editar o fluxo recomendado                     |

#### Léxico 03 - Disciplina

| L03       | Disciplina                                                               |
| --------- | ------------------------------------------------------------------------ |
| Tipo      | Objeto                                                                   |
| Sinônimos | Matéria                                                                  |
| Noção     | Um componente do fluxo. A menor unidade na grade curricular de um curso. |
| Impacto   | Usuário pode receber recomendações de disciplinas                        |

#### Léxico 04 - Disciplina optativa

| L04       | Disciplina optativa                                                                            |
| --------- | ---------------------------------------------------------------------------------------------- |
| Tipo      | Objeto                                                                                         |
| Sinônimos | Matéria optativa                                                                               |
| Noção     | Uma disciplina que pode ser cursada pelo usuário. Não é necessária para terminar sua graduação |
| Impacto   | Usuário pode incluir uma disciplina optativa para que apareça na recomendação                  |
|           | Usuário vai escolher disciplinas optativas de uma lista                                        |
|           | A aplicação deve mostrar quantas horas de disciplinas optativas faltam para o aluno se formar  |

#### Léxico 05 - Disciplina obrigatória

| L05       | Disciplina obrigatória                                                                        |
| --------- | --------------------------------------------------------------------------------------------- |
| Tipo      | Objeto                                                                                        |
| Sinônimos | Matéria optativa                                                                              |
| Noção     | Uma disciplina que deve ser cursada pelo usuário, é necessária para terminar sua graduação    |
| Impacto   | Usuário pode incluir uma disciplina optativa para que apareça na recomendação                 |
|           | Usuário vai escolher disciplinas optativas de uma lista                                       |
|           | A aplicação deve mostrar quantas horas de disciplinas optativas faltam para o aluno se formar |


#### Léxico 06 - Disciplina módulo livre

| L06       | Disciplina módulo livre                                                                                                                                      |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Tipo      | Objeto                                                                                                                                                       |
| Sinônimos | Matéria módulo livre                                                                                                                                         |
| Noção     | As disciplinas de módulo livre de um curso são todas as disciplinas de graduação que não são de abrangência restrita e que não constam no currículo do curso |
| Impacto   | A aplicação deve mostrar quantas horas de disciplinas módulo livre faltam para o aluno se formar                                                             |
|           | Usuário vai escolher disciplinas optativas de uma lista                                                                                                      |
|           | A aplicação deve mostrar quantas horas de disciplinas optativas faltam para o aluno se formar                                                                |

#### Léxico 07 - Disciplina equivalente

| L07       | Disciplina equivalente                                                                                      |
| --------- | ----------------------------------------------------------------------------------------------------------- |
| Tipo      | Objeto                                                                                                      |
| Sinônimos | Matéria equivalente                                                                                         |
| Noção     | uma disciplina que cumpre os mesmos requisitos que outra disciplina, podendo ser escolhida em vez da última |
| Impacto   | ---                                                                                                         |

#### Léxico 08 - Disciplina pré requisito

| L08       | Disciplina pré requisito                                                                                                                      |
| --------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Tipo      | Objeto                                                                                                                                        |
| Sinônimos | Matéria pré requisito                                                                                                                         |
| Noção     | Uma disciplina que deve ser cursada necessariamente antes de outra                                                                            |
| Impacto   | Um usuário só pode cursar uma disciplina se ele cursou todas as suas disciplinas pré requisito e isso deve ser refletido no fluxo recomendado |

#### Léxico 09 - Carga horária

| L09       | Carga horária                                                                                         |
| --------- | ----------------------------------------------------------------------------------------------------- |
| Tipo      | Objeto                                                                                                |
| Sinônimos | Horas de curso                                                                                        |
| Noção     | Quantidade de horas de uma disciplina, de uma categoria de disciplinas ou de um currículo de um curso |
| Impacto   | O usuário deve saber quanto de carga horária terá cada semestre do fluxo recomendado.                 |


#### Léxico 10 - Crédito

| L10       | Crédito                                                                                 |
| --------- | --------------------------------------------------------------------------------------- |
| Tipo      | Objeto                                                                                  |
| Sinônimos | ---                                                                                     |
| Noção     | Unidades que contam o valor de cada disciplina, precisa-se de X créditos para se formar |
| Impacto   | O usuário pode escolher quantos créditos quer cursar por semestre                       |
|           | O usuário pode visualizar quantos créditos cada disciplina vale                         |
|           | O usuário pode visualizar quantos créditos falta para se formar                         |

#### Léxico 11 - Semestre

| L11       | Semestre                                                         |
| --------- | ---------------------------------------------------------------- |
| Tipo      | Objeto                                                           |
| Sinônimos | Período                                                          |
| Noção     | Período no qual o estudante se encontra em sua formação          |
| Impacto   | O usuário pode  visualizar disciplinas recomendadas por semestre |

#### Léxico 12 - Currículo

| L12       | Currículo                                                     |
| --------- | ------------------------------------------------------------- |
| Tipo      | Objeto                                                        |
| Sinônimos | ---                                                           |
| Noção     | Disciplinas que o aluno deve cursar para completar a formação |
| Impacto   | O sistema tem acesso ao currículo de um determinado curso     |

#### Léxico 13 - Curso

| L13       | Curso                                                        |
| --------- | ------------------------------------------------------------ |
| Tipo      | Objeto                                                       |
| Sinônimos | Faculdade                                                    |
| Noção     | Graduação que está sendo estudada                            |
| Impacto   | O sistema recomenda disciplinas com base no curso do usuário |

#### Léxico 14 - Fluxograma 

| L14       | Fluxograma                                              |
| --------- | ------------------------------------------------------- |
| Tipo      | Objeto                                                  |
| Sinônimos | ---                                                     |
| Noção     | Diagrama que apresenta as disciplinas ligadas entre si  |
| Impacto   | O usuário pode visualizar o fluxograma recomendado      |
|           | O usuário pode editar o fluxograma recomendado          |
|           | O usuário pode salvar/exportar o fluxograma recomendado |

### Verbo

#### Léxico 15 - Priorizar

| L15       | Priorizar                                                                           |
| --------- | ----------------------------------------------------------------------------------- |
| Tipo      | Verbo                                                                               |
| Sinônimos | ---                                                                                 |
| Noção     | Estabelecer algo como prioridade, definir algumas disciplinas como mais importantes |
| Impacto   | O usuário pode priorizar as disciplinas que quer ou não cursar no semestre          |

#### Léxico 16 - Recomendar

| L16       | Recomendar                                     |
| --------- | ---------------------------------------------- |
| Tipo      | Verbo                                          |
| Sinônimos | Indicar, sugerir                               |
| Noção     | Ato de indicar algo como bom                   |
| Impacto   | O sistema recomenda disciplinas para o usuário |


#### Léxico 17 - Formar

| L17       | Formar                                                                          |
| --------- | ------------------------------------------------------------------------------- |
| Tipo      | Verbo                                                                           |
| Sinônimos | Diplomar-se, graduar                                                            |
| Noção     | Terminar a faculdade, completar o curso                                         |
| Impacto   | O sistema mostra o fluxo ideal visando o menor caminho para o estudar se formar |

### Estado

#### Léxico 18 - Matriculado

| L18       | Matriculado                                                      |
| --------- | ---------------------------------------------------------------- |
| Tipo      | Estado                                                           |
| Sinônimos | ---                                                              |
| Noção     | O estudante que está cursando uma disciplina                     |
| Impacto   | O sistema mostra as disciplinas que o estudante está matriculado |


## Referências

SERRANO, Milene; SERRANO, Maurício. Requisitos - Aula 10.

REQUISITOS DE SOFTWARE, DisneyPlus 2021.1. Léxicos. Disponível em: <https://requisitos-de-software.github.io/2021.1-DisneyPlus/modelagem/lexicos/#l04-conta>