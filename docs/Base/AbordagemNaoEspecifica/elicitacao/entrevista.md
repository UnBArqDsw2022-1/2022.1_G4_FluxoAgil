# Entrevista

## Histórico de versões

| Data     | Versão | Descrição                           | Autor                                                                                     | Revisor                                |
| -------- | ------ | ----------------------------------- | ----------------------------------------------------------------------------------------- | -------------------------------------- |
| 19/06/22 | 1.0    | Criação do documento                | [Yudi Yamane](https://github.com/yudi-azvd), [Amanda Nobre](https://github.com/AmandaNbr) | [Lucas Braun](https://github.com/lbvx) |
| 23/06/22 | 1.1    | Adição das entrevistas e requisitos | [Yudi Yamane](https://github.com/yudi-azvd), [Amanda Nobre](https://github.com/AmandaNbr) | [Lucas Braun](https://github.com/lbvx) |

## Introdução

A técnica de elicitação por entrevista consiste em fazer uma série de perguntas para uma ou mais pessoas, que podem
fazer parte do público alvo da aplicação. É uma técnica interessante pois permite a resposta livre do entrevistado. 

## Metodologia

As perguntas da entrevista são as seguintes:

1. Você tem dificuldade em se organizar em relação às matérias que você quer se matricular?
2. Como você se organiza em relação às matérias que você quer se matricular em um dado semestre? Você usa alguma ferramenta?
3. Você sente falta de uma ferramenta que facilite a construção e visualização de fluxos de disciplinas? 
(Se a resposta for não, perguntar de novo no final após interagir com o protótipo)
4. O que você acha imprescindível para a sua organização semestral em relação às disciplinas?
	
_Mostrar o [protótipo funcional](https://fluxoagil.herokuapp.com/)_

5. O que você achou? 
6. O que acha que está faltando? Que informações você acha que podiam estar no resultado?
7. O que você mais gostou?
8. Você sabe quantas optativas precisa pegar para se formar no seu curso?
9. Como você desejaria salvar o fluxo recomendado para consultá-lo no futuro?
10. Que sugestões você tem para o nome do app?

## Participantes

- [Amanda Nobre](https://github.com/AmandaNbr)
- [Yudi Yamane](https://github.com/yudi-azvd)

## Resultados

### Entrevistas:

[Entrevista 1](Base/AbordagemNaoEspecifica/elicitacao/entrevista-1.md)

[Entrevista 2](Base/AbordagemNaoEspecifica/elicitacao/entrevista-2.md)

[Entrevista 3](Base/AbordagemNaoEspecifica/elicitacao/entrevista-3.md)

### Requisitos elicitados:

| ID   | Requisitos Funcionais                                                                                                             |
| ---- | --------------------------------------------------------------------------------------------------------------------------------- |
| EV01 | O sistema deve mostrar a ementa da disciplina                                                                                     |
| EV02 | O sistema deve mostrar o horário da disciplina                                                                                    |
| EV03 | O sistema deve mostrar os professores da disciplina                                                                               |
| EV04 | O sistema deve informar pré requisitos da disciplina                                                                              |
| EV05 | O sistema deve informar a metodologia do professor da disciplina                                                                  |
| EV06 | O sistema deve mostrar a qualidade do professor segundo os estudantes                                                             |
| EV07 | O usuário deve poder escolher manualmente as disciplinas                                                                          |
| EV08 | O sistema deve enviar o fluxo final por email para o estudante                                                                    |
| EV09 | O sistema deve dar a opção de download em pdf ou imagem                                                                           |
| EV10 | O sistema deve separar disciplinas obrigatórias e optativas por cor                                                               |
| EV11 | O sistema deve disponibilizar o fluxo de forma interativa, de modo que o usuário possa arrastar disciplinas para outros semestres |
| EV12 | O sistema deve especificar horas em créditos                                                                                      |
| EV13 | O sistema deve oferecer mais de um fluxo, se for o caso                                                                           |
| EV14 | O sistema deve informar quantas horas optativas ainda faltam para completar a graduação                                           |
| EV15 | O sistema deve balancear disciplinas fáceis e difíceis em um semestre                                                             |
| EV16 | O usuário deve poder escolher várias turmas da mesma disciplina                                                                   |
| EV17 | O usuário pode escolher entre tema claro e escuro                                                                                 |
| EV18 | O sistema deve recomendar  optativas segundo o curso do usuário                                                                   |

## Referências

SOMMERVILLE, Ian. Software Engineering. 10. ed. [S. l.]: Pearson, 2016. ISBN 1-292-09613-6.