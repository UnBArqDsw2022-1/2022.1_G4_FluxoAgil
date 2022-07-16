# Diagrama de comunicação

## Histórico de versões
| Data       | Versão | Descrição            | Autor(a)                             | Revisor(a)                                                |
| ---------- | ------ | -------------------- | ------------------------------------ | --------------------------------------------------------- |
| 06/06/2022 | 1.0    | Criação do documento | [Yudi](https://github.com/yudi-azvd) | [Matheus Monteiro](https://github.com/matheusyanmonteiro) |


## Introdução

Assim como o [diagrama de classes](../Modelagem/diagrama-classes.md), o diagrama
de comunicação também utiliza Unified Modeling Language, mas para ilustrar a 
sequência de interações entre objetos de um módulo, como aconteceria em tempo
de execução.

## Metodologia

O diagrama de comuniciação foi confeccionado com base na experiência prévia 
dos participantes desenvolvendo aplicações web e observando o diagrama de classes.
A ferramenta utilizada foi o Diagrams.net.

## Participantes

- [Yudi Yamane](https://github.com/yudi-azvd)

## Resultados

A Figura 1 ilustra o caminho feliz da aplicação. O usuário, através do navegador,
envia uma requisição POST para o 
`fluxo-agil-server`. O Flask REST invoca o método `post` de um objeto 
`AcademicHistoryController`
`FlowController`, que extrai as informações do corpo da requisição e as
redireciona para um objeto `ExtractAcademicHistoryDataUseCase` pelo método 
`execute`. Este, por sua vez utiliza um objeto capaz de realizar o parse de um 
documento em PDF e retorna as informações desejadas (créditos, disciplinas já
cursadas, ID do currículo e etc). Essas informações são retornas para o usuário.

Em uma nova requisição POST, o usuário causa a invocação do método `post` de
`FlowController`. Esse objeto extrai as informações do corpo da requisição e as
redireciona para um objeto `CalculateFlowUseCase` pelo método `execute`. O objeto
`CalculateFlowUseCase` consulta o currículo desejado pelo usuário através do 
método `getById`. Com o currículo e os dados da requisição em mãos, o método 
`execute` de `LibPreRequisiteSolver` é chamado para finalmente devolver a 
recomendação no formato `Course[][]` para o usuário.

<p align = "center"> <img alt="Diagrama de Comunicação" src="images/modelagem/diagramas-dinamicos-comunicacao.png"/> </p>
<p align = "center">
Figura 1 - Diagrama de comunicação, caminho feliz <br>
Fonte: Diagrams.net
</p>
<br/>

A Figura 2 ilustra um caso de exceção. A primeira parte (1.*) acontece assim 
como na Figura 1. Entretanto, pode acontecer que o arquivo esteja corrompido de 
alguma forma e o identificador do currículo pode ser lido errado. 

<p align = "center"> <img alt="Diagrama de Comunicação" src="images/modelagem/diagramas-dinamicos-comunicacao-2.png"/> </p>
<p align = "center">
Figura 2 - Diagrama de comunicação, caso de exceção <br>
Fonte: Diagrams.net
</p>
<br/>

Nesse caso, na
etapa 2.2 da Figura 2, o método `getById` falha e retorna uma exceção. Nessa
parte do diagrama, foi tomada uma liberadde pela parte do autor para deixar mais
claro que a rotina é interrompida por um `CurriculumNotFoundException`. Note que
o objeto de `LibPreRequisiteSolver` não é invocado. A exceção sobe a callstack
até a controladora que retorna uma mensagem de erro para o navegador do usuário.

## Referências

<!-- https://referenciabibliografica.net/a/pt-br/ref/abnt -->

FAKHROUTDINOV, Kirill. UML Communication Diagrams Overview. 6 ago. 2011. 
Disponível em: https://www.uml-diagrams.org/communication-diagrams.html. Acesso 
em: 12 jul. 2022.
