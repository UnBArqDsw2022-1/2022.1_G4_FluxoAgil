# Diagrama de classes

## Histórico de versões
| Data       | Versão | Descrição            | Autor(a)                                                                                                                      | Revisor(a)                               |
| ---------- | ------ | -------------------- | ----------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- |
| 06/06/2022 | 1.0    | Criação do documento | [Thaís Rebouças](https://github.com/Thais-ra), [Yudi](https://github.com/yudi-azvd), [Irwin](https://github.com/irwinschmitt) | [Irwin](https://github.com/irwinschmitt) |


## Introdução

Diagramas de classes são desenhos técnicos que usam Unified Modeling Language 
(UML) para expressar entidades de um sistema em classes (attributos para suas 
características e métodos para seu compartamentos) e interfaces. Além disso, 
diagramas de classes também podem apresentar diferentes relacionamentos entre as
classes.

**Classe:** componente básico. É uma caixa com o nome da classe em Pascal Case
e em negrito. O nome de uma classe geralmente é um substantivo no singular.

**Relacionamento:** ligações (linhas) entre classes. Podem ser dos tipos: dependência
(mais básico), associação, agregação, composição. Esses tipos de relacionamentos são 
representados pode diferentes terminações nas linhas (seta, losango fechado/aberto,
triângulo etc). 

Nas pontas de um relacionamento também podem ser expressadas a sua cardinalidade:
um pra um, um pra muitos (e vice versa) e muitos pra muitos.

## Metodologia

As dicussões para elaborar o diagrama de classes foram realizadas presencialmente
e por Telegram.

Para começar o diagrama, os participantes analizaram o documento de 
[léxico](../Base/AbordagemNaoEspecifica/lexico.md) para extrair as principais
entidades, seus atributos e relacionamentos. Também foi analisado, brevemente, o 
documento de [requisitos priorizados](../Base/AbordagemNaoEspecifica/priorizacao/moscow.md)
para extrair alguns comportamentos. Foi possível também adiantar a utilização
de alguns padrões de projeto.

A ferramenta utilizada para confeccionar o diagrama foi o Diagrams.net (antigo
Draw.io).

## Participantes

- [Thaís Rebouças](https://github.com/Thais-ra)
- [Yudi Yamane](https://github.com/yudi-azvd)
- [Irwin Schimitt](https://github.com/irwinschmitt)

## Resultados

As principais entidades do domínio que se tornaram classes foram: Curriculum, 
Graduation e Course e CourseType, que está mais para uma enumeração. O 
relacionamento entre eles está representado na Figura 1.

<p align="center"> <img alt="Diagrama de Classes: entidades" 
  src="images/modelagem/diagramas-estaticos-classes-1.png"/> </p>
<p align="center">
Figura 1 - Diagrama de classes das entidades<br>
Fonte: Diagrams.net
</p>

<br/>

Uma disciplina (`Course`) pode ser dos tipos `mandatory`, `optional` ou 
`módulo livre` (até o momento não encontramos o termo apropriado em inglês).

Uma graduação (`Graduation`) pode ter vários currículos (`Curriculum`),
cada um com suas datas de início de vigência. Dado um currículo, a graduação
e suas disciplinas obrigatórias e optativas são definidas e assim é possível 
calcular a recomendação de um fluxo.

A Figura 2 mostra quais classes são utilizadas desde a requisição HTTP até a
camada de dados.

<p align="center"> <img alt="Diagrama de Classes: controladoras e casos de uso" 
  src="images/modelagem/diagramas-estaticos-classes-2.png"/> </p>
<p align="center">
Figura 1 - Diagrama de classes: controladoras e casos de uso<br>
Fonte: Diagrams.net
</p>

Por exemplo, o frontend faz uma requisição HTTP POST na rota `/flow` com os 
dados necessários para o cálculo. A controladora `FlowController` intercepta a 
requisição, extrai os dados entrados pelo usuário e os repassa para um objeto
da classe `CalculateFlowUseCase`.

Por injeção de dependência, `CalculateFlowUseCase` recebe 1) um algoritmo para
resolver as disciplinas pré requisitos e 2) um objeto com acesso ao banco de dados
para consultar currículos.

1) Para maior flexibilidade, a resolução das disciplinas deve estar embrulhada
em um objeto de classe que implementa `IPreRequisiteSolver`. Atualmente, pretendemos
utilizar uma biblioteca para resolver isso. Entretanto, pode ser que no futuro a equipe 
deseje implementar o próprio algoritmo. Essa configuração minimiza os riscos 
de fazer essa troca.

2) Para calcular a recomendação de fluxo, `CalculateFlowUseCase` precisa de acesso
aos currículos e para isso é usado o padrão de repositório em 
`CurriculumRepository`, que é injetado como dependência.


## Referências

<!-- https://referenciabibliografica.net/a/pt-br/ref/abnt -->

FAKHROUTDINOV, Kirill. UML Class and Object Diagrams Overview. 6 ago. 2011. 
Disponível em: https://www.uml-diagrams.org/class-diagrams-overview.html. Acesso 
em: 6 jul. 2022.

CLASS diagram. [S. l.], 24 ago. 2005. Disponível em: 
https://en.wikipedia.org/wiki/Class_diagram. Acesso em: 7 jul. 2022.