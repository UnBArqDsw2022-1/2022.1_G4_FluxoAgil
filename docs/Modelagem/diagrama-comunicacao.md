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

<p align = "center"> <img alt="Diagrama de Comunicação" src="images/modelagem/diagramas-dinamicos-comunicacao.png"/> </p>
<p align = "center">
Figura 1 - Diagrama de comunicação <br>
Fonte: Diagrams.net
</p>

Esse diagrama ilustra apenas uma das requisições que acontece no servidor.

O usuário, através do navegador, envia uma requisição POST para o 
`fluxo-agil-server`. O Flask REST invoca o método `post` de um objeto 
`FlowController`, que extrai as informações do corpo da requisição e as
redireciona para um objeto `CalculateFlowUseCase` pelo método `execute`. O objeto
`CalculateFlowUseCase` consulta o currículo desejado pelo usuário através do 
método `getById`. Com o currículo e os dados da requisição em mãos, o método 
`execute` de `LibPreRequisiteSolver` é chamado para finalmente devolver a 
recomendação para o usuário.

## Referências

<!-- https://referenciabibliografica.net/a/pt-br/ref/abnt -->

FAKHROUTDINOV, Kirill. UML Communication Diagrams Overview. 6 ago. 2011. 
Disponível em: https://www.uml-diagrams.org/communication-diagrams.html. Acesso 
em: 12 jul. 2022.
