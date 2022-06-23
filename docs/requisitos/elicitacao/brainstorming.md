# Brainstorming

## Histórico de versões
| Data       | Versão | Descrição            | Autor(a)                                     | Revisor(a)                                    |
| ---------- | ------ | -------------------- | -------------------------------------------- | --------------------------------------------- |
| 18.06.22   | 1.0   | Criação do documento | [Matheus Monteiro](https://github.com/matheusyanmonteiro) | [Amanda Nobre](https://github.com/AmandaNbr)|

## Introdução

A técnica de elicitação através do brainstorming é baseada em uma reunião, como um espaço pré-definido, entre os engenheiros de requisitos. O objetivo principal é explorar as ideias e interagir com outros participantes onde todos podem compartilhar suas opiniões. Assim, listando um número significativo de requisitos, visando entneder o que os usuarios do sistema querem e precisam. Por padrão está técnica é utilizada no inicio do processo de elicitação, quando muito pouco do projeto e do processo é conhecido. 

## Metodologia

A equipe optou por fazer essa técnica no remoto onde foi separado uma reunião longa onde cada um dos integrantes tinham acesso ao miro (quadro branco online) e ao discord (plataforma de comunicação) possibilitando que todos tenham voz e a organização.


## Participantes

- Ana Carolina (https://github.com/AnaCarolinaRodriguesLeite)
- Matheus Monteiro (https://github.com/matheusyanmonteiro)
- Matheus Pinheiro (https://github.com/matheuscvp)
- Matheus Fonseca (https://github.com/gatotabaco)
- Mateus Maia (https://github.com/mateusmaiamaia)
- Thais Rebouças (https://github.com/Thais-ra)
- Irwin Schmitt (https://github.com/irwinschmitt)
- Lucas Braun (https://github.com/lbvx)
- Yudi Yamane (https://github.com/yudi-azvd)
- Amanda Nobre (https://github.com/AmandaNbr)


## Resultados

Com Resultado da discursão e das ideias dos participantes, os seguintes requisitos foram levantados. 

| Número | ID    |                                        Requisitos Funcionais                                        | 
| ---------- | ------ | ---------------------------------------------------------------------------------------------------- |
|   1    | BS01 |  O usuario deve enviar o histórico                                        |
|   2    | BS02 |  O usuario deve poder selecionar disciplinas manualmente                  |
|   3    | BS03 |  O usuario deve escolher a quantidade de creditos que deseja cursar no semestre               |
|   4    | BS04 |  O sistema deve levar em consideração se o usuario esa cursando alguma disciplina no momento         |
|   5    | BS05 |  O sistema deve recomendar o fluxo atualizado                                             |
|   6    | BS06 |  O usuario pode ajustar quais diciplinas ele não quer cursar                                       |
|   7    | BS07 |  O usuario deve ajustar as diciplinas optativas que deseja cursar                                 |
|   8    | BS08 |  O sistema deve Mostrar a quantidade de horas já escolhidas                                      |
|   9   | BS09 |  O sistema deve mostrar quantas diciplinas optativas faltam para formação                    |
|   10   | BS10 |  O sistema deve mostrar quantas diciplinas obrigatórias faltam para formação                 |
|   11   | BS11 |  O sistema deve informar caso o usuario já tenha feito todas as disciplinas optativas             |
|   12   | BS12 |  O sistema deve alertar caso a precisão de pegar materias optativas                              |
|   13   | BS13 |  O usuario poderá consultar um fórum com recomendações de outros alunos                           |
|   14   | BS14 |  O sistema deverá mostrar os prés-requisitos das materias que deveram ser feitas no  futuro        |
|   15   | BS15 |  O sistema devera mostrar quais materias poderão ser feitas por já terem pre requisitos contemplados |
|   16   | BS16 |  O sistema deve permitir setar manualmente uma disciplina para cursar  em um semestre especifico a frente     |
|   17   | BS17 |  O sistema deverá permitir a personalização do fluxograma gerado                 |
|   18   | BS18 |  O sistema deverá permitir a comparação com dois fluxogramas diferentes          |
|   19   | BS19 |  O sistema devera diferenciar as diciplinas obrigatórias e optativas com cores diferentes    |
|   20   | BS20 |  O sistema deverá salvar o fluxo de recomendação em pdf para o usuario              |
|   22   | BS22 |  O sistema devera conter uma tecla para compartilhamento do fluxo de recomendação        |
|   23   | BS23 |  O sistema devera gerar um fluxo com as materias que o usuario deverá pegar o quanto antes  |
|   24   | BS24 |  O sistema deverá apresentar para o usuario o fluxo original de cada semestre       |
|   25   | BS25 |  O sistema deverá contabilizar em quantos semestres o usuario terá sua formação       |
|   26   | BS26 |  O sistema deverá recomendar baseado nas diciplinas feitas no passado           |
|   27   | BS27 |  O sistema devera informar a descrição da disciplina                           |
|   28   | BS28 |  O sistema devera mostrar se o usuario pode pegar disciplina de tcc ou estagio    |
|   29   | BS29 |  O sistema deverá mostrar a porcentagem que falta para a formação  |
|   30   | BS30 |  O sistema deverá calcular o número medio de creditos para a formação    |
|   31   | BS31 |  O sistema deverá saber se dado semestre o fluxo de horarios gera conflitos com materias obrigatórias   |
|   32   | BS32 |  O sistema deverá mostrar os professores que ministram cada disciplina                            |
|   33   | BS33 |  O sistema deverá obter informações de currículo/disciplina automaticamente |
|   34   | BS34 |  O sistema deverá atualizar currículos/disciplinas semestralmente  |
|   35   | BS35 |  O sistema deverá salvar currículos/disciplinas em uma base de dados   |

<figcation>Tabela 1: Requisitos funcionais. </figcation>

### Requistios não funcionais

| Número | ID    |                                   Requisitos Não Funcionais                                    |
| ---------- | ------ | ---------------------------------------------------------------------------------------------------- |
|   1    |   BS36   |                  O sistema deve ser responsivo                                             |
|   2    |   BS37   | O sistema deve ter consistência entre recomendações                                        |
|   3    |   BS38   | O sistema resolver os problemas de pré requisitos                                              |
|   4    |   BS39   | O sistema deve ter navegabilidade fácil                                                        |
|   5    |   BS40   | O sistema deverá tratar pdf de historico inválidos                                             |


<figcation>Tabela 2: Requisitos não funcionais. </figcation>
## Referências

- REQUISITOS funcionais e requisitos não funcionais. 2021. Disponível em: https://codificar.com.br/requisitos-funcionais-nao-funcionais/#:~:text=Os%20requisitos%20funcionais%20descrevem%20o,que%20o%20sistema%20deve%20ter.. Acesso em: 18 jun. 2022.

- O QUE são requisitos funcionais e não funcionais. 2022. Disponível em: https://analisederequisitos.com.br/requisitos-funcionais-e-nao-funcionais/. Acesso em: 18 jun. 2022.
