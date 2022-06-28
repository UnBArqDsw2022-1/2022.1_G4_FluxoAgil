# MoSCoW

## Histórico de versões

| Data     | Versão | Descrição            | Autor(a)                                      | Revisor(a)                                       |
| -------- | ------ | -------------------- | --------------------------------------------- | ------------------------------------------------ |
| 26/06/22 | 1.0    | Criação do documento | [Thaís Rebouças](https://github.com/Thais-ra) | [Matheus Calixto](https://github.com/matheuscvp) |


## Introdução

Nem todos os requisitos devem ser imediatamente implementados. Por isso existe um processo de priorização de requisitos, no qual são definidos aqueles que têm mais importância no momento e, portanto, devem ser implementados primeiro.</br>
O MoSCoW é uma técnica de priorização onde cada requisito é classificado entre Must, Should, Could e Won't.

- Must: Algo que deve ser feito agora;
- Should: Algo que deveria fazer mas não necessariamente agora;
- Could: Algo que poderia ser feito;
- Won't: Algo que não deve ser feito por enquanto.
  

## Metodologia

Foi criado uma tabela no planilhas google onde cada membro indicou sua opinião entre as classificações MoSCoW. Para facilitar a classificação substituímos must por 1, should por 2, could por 3 e won't por 4, a partir disso foi feito uma média para definir a classificação final.
  

## Participantes

  
- [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite)
- [Amanda Nobre](https://github.com/AmandaNbr)
- [Irwin Schmitt](https://github.com/irwinschmitt)
- [Lucas Braun](https://github.com/lbvx)
- [Matheus Fonseca](https://github.com/gatotabaco)
- [Mateus Maia](https://github.com/mateusmaiamaia)
- [Matheus Calixto](https://github.com/matheuscvp)
- [Thais Rebouças](https://github.com/Thais-ra)
- [Yudi Yamane](https://github.com/yudi-azvd)

  

## Resultados

### Requisitos Funcionais
  
| Id   | Requisito                                                                                                                      | Prioridade |
| ---- | ------------------------------------------------------------------------------------------------------------------------------ | ---------- |
| RF01 | O usuário deve poder enviar o histórico para informar ao sistema quais disciplinas que já cursou                               | Must       |
| RF02 | O usuário deve poder selecionar manualmente as disciplinas que já cursou                                                       | Would      |
| RF03 | O usuário deve poder escolher a quantidade de créditos que deseja cursar em cada semestre                                      | Must       |
| RF04 | O usuário deve poder selecionar as disciplinas que esta cursando no momento                                                    | Must       |
| RF05 | O usuário deve receber uma recomendação de fluxo com as disciplinas que deve cursar no próximos semestres até se formar        | Must       |
| RF06 | O usuário deve poder salvar a recomendação de fluxo                                                                            | Would      |
| RF07 | O usuário deve poder compartilhar a recomendação de fluxo                                                                      | Could      |
| RF08 | O usuário deve poder enviar a recomendação de fluxo por email                                                                  | Won't      |
| RF09 | O usuário deve poder selecionar optativas que deseja cursar                                                                    | Must       |
| RF10 | O sistema deve informar quantas horas pendentes de optativas faltam para formação                                              | Must       |
| RF11 | O sistema deve mostrar quantas disciplinas obrigatórias faltam para formação                                                   | Must       |
| RF12 | O sistema deve recomendar optativas segundo o curso do usuário                                                                 | Would      |
| RF13 | O sistema deve mostrar a quantidade de horas já escolhidas                                                                     | Would      |
| RF14 | O sistema deve mostrar a porcentagem que falta para a formação                                                                 | Would      |
| RF15 | O sistema deve informar qual é a quantidade mínima de semestres para se formar                                                 | Must       |
| RF16 | O usuário deve poder escolher o semestre em que cursar determinada disciplina                                                  | Could      |
| RF17 | O usuário deve poder escolher quando não cursar uma disciplina                                                                 | Would      |
| RF18 | O usuário deve poder escolher quais disciplinas não deseja cursar juntas                                                       | Could      |
| RF19 | O sistema deve mostrar os pré-requisitos das disciplinas na recomendação gerada                                                | Must       |
| RF20 | O usuário deve poder visualizar quais disciplinas podem ser feitas a partir de uma selecionada na recomendação de fluxo gerada | Could      |
| RF21 | O usuário deve poder interagir com o fluxo, arrastando disciplinas para outros semestres                                       | Could      |
| RF22 | O sistema deve permitir a adição de disciplinas à recomendação de fluxo gerado                                                 | Won't      |
| RF23 | O sistema deve recomendar mais de um fluxo                                                                                     | Won't      |
| RF24 | O sistema deve permitir a comparação entre recomendações diferentes                                                            | Won't      |
| RF25 | O sistema deve diferenciar as disciplinas obrigatórias e optativas por cor                                                     | Would      |
| RF26 | O sistema deve apresentar o fluxo original de cada semestre                                                                    | Won't      |
| RF27 | O usuário deve poder visualizar a descrição da disciplina                                                                      | Could      |
| RF28 | O sistema deve obter informações de currículo                                                                                  | Must       |
| RF29 | O sistema deve obter informações de disciplina                                                                                 | Must       |
| RF30 | O sistema deve mostrar o horários das turmas disciplinas                                                                       | Could      |
| RF31 | O sistema deve recomendar um fluxo onde os horários das disciplinas não geram conflitos                                        | Won't      |
| RF32 | O sistema deve informar a metodologia do professor da disciplina                                                               | Won't      |
| RF33 | O sistema deve mostrar os professores que ministram cada disciplina                                                            | Won't      |
| RF34 | O sistema deve mostrar a qualidade do professor segundo os estudantes                                                          | Won't      |
| RF35 | O usuario deve poder consultar um fórum com recomendações de outros alunos                                                     | Won't      |
| RF36 | O sistema deve converter horas em créditos                                                                                     | Would      |
| RF37 | O usuário deve poder escolher várias turmas da mesma disciplina                                                                | Won't      |
| RF38 | O usuário deve poder escolher entre tema claro e escuro                                                                        | Could      |


### Requisitos Não Funcionais

| Id    | Requisito                                                                                               | Prioridade |
| ----- | ------------------------------------------------------------------------------------------------------- | ---------- |
| RNF01 | O sistema deve salvar currículos/disciplinas em uma base de dados                                       | Must       |
| RNF02 | O sistema deve manter o currículo dos cursos atualizado com o sigaa                                     | Must       |
| RNF03 | O sistema deve gerar um fluxo com as materias que o usuario deverá pegar o quanto antes                 | Must       |
| RNF04 | O sistema deve informar como funciona e utilizar a aplicação                                            | Must       |
| RNF05 | O sistema deve sempre mostrar a mesma recomendação se as mesmas opções e disciplinas forem selecionados | Would      |
| RNF06 | O sistema deve ser responsivo                                                                           | Must       |
| RNF07 | O sistema deve informar o estado atual da aplicação                                                     | Would      |
| RNF08 | O sistema deve recomendar um fluxo de acordo com os pré-requisitos das disciplinas                      | Must       |
| RNF09 | O sistema deve recomendar um fluxo de acordo com os co-requisito das disciplinas                        | Must       |
| RNF10 | O sistema deve recomendar um fluxo de acordo com os pré-requisitos de porcentagem de curso              | Must       |
| RNF11 | O sistema deve ter navegabilidade fácil                                                                 | Must       |
| RNF12 | O sistema deve tratar pdf de histórico inválidos                                                        | Would      |



## Referências

Railsware Product Academy. MoSCoW prioritization for your product backlog. Youtube, 19 de Setembro de 2019. Disponível em: https://www.youtube.com/watch?v=DzruAbBhY0Q. Acesso em: 26 de Junho de 2022.

INFINITY, Task Prioritization with MoSCoW Method. Disponível em: https://startinfinity.com/product-management-framework/product-backlog/task-prioritization-using-moscow-method. Acesso em: 26 de Junho de 2022.
