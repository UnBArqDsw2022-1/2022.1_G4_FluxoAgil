# Léxicos

## Histórico de versões
| Data       | Versão | Descrição            | Autor                                       | Revisor                                      |
| ---------- | ------ | -------------------- | ------------------------------------------- | -------------------------------------------- |
| 19.06.2022 | 1.0    | Criação do documento | [Yudi Yamane](https://github.com/yudi-azvd) | [Amanda Nobre](https://github.com/AmandaNbr) |

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

| L01       | Duração                                                     |
| --------- | ----------------------------------------------------------- |
| Tipo      | Objeto                                                      |
| Sinônimos | Aluno                                                       |
| Noção     | Indivíduo que pretende utilizar o sistema                   |
| Impacto   | O usuário envia o histórico acadêmico                       |
|           | O usuário pode visualizar o tempo de duração de um episódio |
|           | O usuário escolhe matérias específicas                      |
|           | O usuário recebe recomendação do fluxo ideal                |

#### Léxico 02 - Fluxo

| L01       | Duração                                                         |
| --------- | --------------------------------------------------------------- |
| Tipo      | Objeto                                                          |
| Sinônimos | -                                                               |
| Noção     | Caminho de matérias a serem seguidas recomendadas pelo software |
| Impacto   | O sistema recomenda um fluxo ideal                              |
|           | O usuário poderá editar o fluxo recomendado                     |


<!-- 

### ESTADO

#### Léxico 01 - Duração

Usuário objeto
Noção:  Indivíduo que pretende utilizar o sistema
Impacto: 
  O usuário envia o histórico acadêmico
  O usuário escolhe matérias específicas
  O usuário recebe recomendação do fluxo ideal
Sinônimo: Aluno



### VERBO

#### Léxico 17 - Reproduzir

| L17       | Reproduzir                                                            |
| --------- | --------------------------------------------------------------------- |
| Tipo      | Verbo                                                                 |
| Sinônimos | Apresentar, exibir, dar play, ouvir                                   |
| Noção     | O usuário reproduz um episódio de um PodCast                          |
| Impacto   | O usuário pode pausar o episódio                                      |
|           | O usuário pode avançar 30 segundos e retornar 10 segundos no episódio |
|           | O usuário pode avançar outro episodio da fila                         |
|           | O usuário pode mudar a velocidade de reprodução                       |

 -->
## Referências

SERRANO, Milene; SERRANO, Maurício. Requisitos - Aula 10.

REQUISITOS DE SOFTWARE, DisneyPlus 2021.1. Léxicos. Disponível em: <https://requisitos-de-software.github.io/2021.1-DisneyPlus/modelagem/lexicos/#l04-conta>