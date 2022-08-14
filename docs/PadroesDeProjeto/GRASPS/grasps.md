# Padrões de Projeto GRASP(s)

## Histórico de versões
| Data     | Versão | Descrição                                               | Autor(a)                                                                                                    | Revisor(a) |
| -------- | ------ | ------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | ---------- |
| 31/07/22 | 1.0    | Criação do documento                                    | [Amanda Nobre](https://github.com/AmandaNbr) e [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite) | [Matheus Fonseca](https://github.com/gatotabaco)           |
| 08/08/22 | 1.1    | Inserção da definição de GRASPS, criador e especialista | [Amanda Nobre](https://github.com/AmandaNbr) e [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite) | [Matheus Fonseca](https://github.com/gatotabaco)           |

## Introdução

Esse documento tem como objetivo explicitar os padrões de projetos grasps que a equipe visa utilizar ao decorrer do desenvolvimento do projeto para elevar a qualidade técnica do código 
ao seguir os padrões e práticas que serão explicitados.

Os padrões de projeto GRASP (General Responsibility Assignment Software Patterns), consistem em práticas para atribuição de responsabilidades, para classes e objetos, em projetos orientados a objetos.

Estes padrões de projeto foram publicados originalmente pelo especialista Craig Larman no livro “Applying UML and Patterns – An Introduction to Object-Oriented Analysis and Design and the Unified Process” (obra traduzida em português com o título “Utilizando UML e Padrões – Uma introdução à análise e ao projeto orientados a objetos e ao desenvolvimento iterativo”).

O conceito de responsabilidade deve ser compreendido, basicamente, como as obrigações que um objeto possui quando se leva em conta o seu papel dentro de um determinado contexto. Além disso, é preciso considerar ainda as prováveis colaborações (interações) entre diferentes objetos. Cada padrão GRASP está melhor detalhado abaixo.

## Metodologia

A equipe dividiu pares em uma reunião pelo Discord, estes pares ficaram responsáveis cada um por buscar um grasp que condiz com o projeto e que é viável de ser seguido, após isso houve um debate a respeito das escolhas da equipe e a criação do documento.


## Participantes

- [Amanda Nobre](https://github.com/AmandaNbr)
- [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite)

## Resultados

<!-- Criador; Especialista na Informação; Alta Coesão; Baixo Acoplamento; Controlador; Polimorfismo; Indireção; Fabricação ou Invenção Pura e Variações Protegidas.-->

## Criador
Uma atividade muito importante para um sistema de orientação a objetos é a criação de um objeto. Com base nisso, torna-se uma atividade fundamental identificar qual classe será responsável pela criação de determinado objeto. Diante desse contexto há o padrão Criador que determina qual classe deve ser responsável pela criação do objeto. Atribua à classe B a responsabilidade de criar uma instância da classe A se:

1. B agrega objetos de A
2. B contém A
3. B armazena instância de A
4. B usa objetos de A
5. B possui informação necessária à criação de A

### Uso no projeto

<img src="images/GRASPS/Criador.png" align = "center" />
<p align = "center"> 
Figura 1 - Exemplo de criador <br>
Autora:  Ana Carolina
</p>

A imagem acima é uma retratação de uma modelagem do projeto que se encaixa no padrão de projeto GRASP Criador. No exemplo, a classe Curriculum é a classe responsável por instanciar os objetos da classe Graduation e Course. Isso significa que cada objeto Curriculum é o responsável por criar seus próprios Graduation e Course, visto que ele detém as informações necessárias para tal atividade.


## Especialista
O princípio de especialista na informação é utilizado para atribuir responsabilidades. Consiste em delegar a responsabilidade à quem possui as informações necessárias para cumpri-la. Para isso primeiro é identificado qual seria a informação e em seguida onde ela foi armazenada, viabilizando assim o acesso da informação e, consequentemente, a atribuição.

### Uso no projeto
Justificativa: Evita a criação de soluções desnecessariamente complexas e estimula a análise de qual seria mais objetiva.


## Alta coesão
A Alta Coesão diz respeito ao problema de manter os objetos bem focados, com 
propósitos claros e gerenciáveis, uma vez que é bastante comum começar o desenvolvimento com uma classe enxuta e ao longo do processo ela ir crescendo desenfreadamente, 
e tendo que executar um grande volume de trabalho, ou seja, grande parte do funcionamento do sistema irá depender de um ponto, e esse está longe de ser o ideal.

![image](https://user-images.githubusercontent.com/44625056/184447382-e1dfa6b1-980b-42a8-ade5-29988894a07a.png)

### Uso no projeto
A Alta Coesão é um dos padrões que é focado como objetivo desde a diagramação, uma vez que cada classe terá objetivos e responsabilidades claras, melhorando a compreensão sobre as classes,
tendo boa reutilização e maior manutenibilidade. É possível notar essa prática atraves do [diagrama de classes](Modelagem/diagrama-classes.md).


## Baixo acoplamento
O acoplamento de um sistema é a relação entre os elementos e quanto eles são dependentes entre si. Dessa forma, o ideal é que o acoplamento seja baixo, pois assim o entendimento geral melhora, 
auxilia a reutilização e modificações geram menos impacto. Importante lembrar que o menor grau de acoplamento é quando não há acoplamento, sendo assim por mais que desejarmos diminuir o 
acoplamento, é necessário existir acoplamento.

![image](https://user-images.githubusercontent.com/44625056/184447487-cb875ada-aac2-43da-bfd9-d4765b70c8d7.png)

### Uso no projeto
O baixo acoplamento é notável através do [diagrama de classes](Modelagem/diagrama-classes.md).


## Referências

Understanding the GRASP Design Patterns. Disponível em https://medium.com/@ReganKoopmans/understanding-the-grasp-design-patterns-2cab23c7226e. Acesso em 08 de agosto de 2022.

Padrões de Projeto. Disponível em <https://refactoring.guru/pt-br/design-patterns>. Acesso em 08 de agosto de 2022.

SERRANO, Milene. Arquitetura e Desenho de Software. AULA - GRASP – PARTE I e II. Acesso em 08 de agosto de 2022.
