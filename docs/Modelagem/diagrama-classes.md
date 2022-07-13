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

**Classe:** compoenete básico. É uma caixa com o nome da classe em Pascal Case
e em negrito. O nome de uma classe geralmente é um substantivos no singular.

**Relacionamento:** ligações (linhas) entre classes. Podem ser dos tipos: dependência
(mais básico), associação, agregação, composição. Esses tipos de relacionamentos são 
representados pode diferentes terminações nas linhas (seta, losango fechado/aberto,
triângulo etc). 

Nas pontas de um relacionamento também podem ser expressada a sua cardinalidade:
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

As principais entidades que se tornaram classes foram: Curriculum, Graduation e 
Course e CourseType, que está mais para uma enumeração.

<p align = "center"> <img alt="Diagrama de Classes" src="images/modelagem/diagramas-estaticos-classes.png"/> </p>
Figura 1 - Diagrama de classes <br>
Fonte: Draw.io
</p>

## Referências

<!-- https://referenciabibliografica.net/a/pt-br/ref/abnt -->

FAKHROUTDINOV, Kirill. UML Class and Object Diagrams Overview. 6 ago. 2011. 
Disponível em: https://www.uml-diagrams.org/class-diagrams-overview.html. Acesso 
em: 6 jul. 2022.

CLASS diagram. [S. l.], 24 ago. 2005. Disponível em: 
https://en.wikipedia.org/wiki/Class_diagram. Acesso em: 7 jul. 2022.