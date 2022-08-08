# Padrões de Projeto GRASP(s)

## Histórico de versões
| Data     | Versão | Descrição            | Autor(a)                                           | Revisor(a) |
| -------- | ------ | -------------------- | -------------------------------------------------- | ---------- |
| 31/07/22 | 1.0    | Criação do documento | [Amanda Nobre](https://github.com/AmandaNbr) e [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite) | -          |
| 08/08/22 | 1.1    | Inserção da definição de GRASPS, criador e especialista | [Amanda Nobre](https://github.com/AmandaNbr) e [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite) | -          |

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

### Criador
Uma atividade muito importante para um sistema de orientação a objetos é a criação de um objeto. Com base nisso, torna-se uma atividade fundamental identificar qual classe será responsável pela criação de determinado objeto. Diante desse contexto há o padrão Criador que determina qual classe deve ser responsável pela criação do objeto. Atribua à classe B a responsabilidade de criar uma instância da classe A se:

1. B agrega objetos de A
2. B contém A
3. B armazena instância de A
4. B usa objetos de A
5. B possui informação necessária à criação de A

#### Uso no projeto

<img src="img/GRASPS/Criador.png" align = "center" />
<p align = "center"> 
Figura 1 - Exemplo de criador <br>
Fonte (ou Autor):  Ana Carolina
</p>


A imagem acima é uma retratação de uma modelagem do projeto que se encaixa no padrão de projeto GRASP Criador. No exemplo, a classe Curriculum é a classe responsável por instanciar os objetos da classe Graduation e Course. Isso significa que cada objeto Curriculum é o responsável por criar seus próprios Graduation e Course, visto que ele detém as informações necessárias para tal atividade.

### Especialista
O princípio de especialista na informação é utilizado para atribuir responsabilidades. Consiste em delegar a responsabilidade à quem possui as informações necessárias para cumpri-la. Para isso primeiro é identificado qual seria a informação e em seguida onde ela foi armazenada, viabilizando assim o acesso da informação e, consequentemente, a atribuição.

#### Uso no projeto
Justificativa: Evita a criação de soluções desnecessariamente complexas e estimula a análise de qual seria mais objetiva.


### Baixo acoplamento

### Alta coesão
Resultados da técnica/artefato.

*Para imagens é necessário seguir a formatação:

(IMAGEM) <br>
Figura n - Título da imagem <br>
Autor ou Fonte

Exemplo:
<img src="img/heatmap.jpeg" align = "center" />
<p align = "center"> 
Figura 1 - Heatmap da Equipe <br>
Fonte (ou Autor): Amanda 
</p>

## Referências

Understanding the GRASP Design Patterns. Disponível em: https://medium.com/@ReganKoopmans/understanding-the-grasp-design-patterns-2cab23c7226e. Acesso em: 08/08/2022