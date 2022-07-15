# Modelagem do Banco de Dados

## Histórico de versões
| Data     | Versão | Descrição                      | Autor(a)                                      | Revisor(a)                                                   |
| -------- | ------ | ------------------------------ | --------------------------------------------- | ------------------------------------------------------------ |
| 13/07/22 | 1.0    | Criação do documento           | [Thaís Rebouças](https://github.com/Thais-ra) | [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite) |
| 14/07/22 | 1.1    | Adição da introdução, metodologia, diagramas, tabelas e referências | [Thaís Rebouças](https://github.com/Thais-ra) | [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite) e [Matheus Monteiro](https://github.com/matheusyanmonteiro)|


## Introdução

Modelagem de banco de dados é o processo de levantamento, análise, categorização e exploração de todos os dados e tipos de informações que irão sustentar uma aplicação. Esta é uma etapa primordial no trabalho do desenvolvimento de sistemas, porque todo software é criado com determinados objetivos, para atender às necessidades dos usuários dentro deste cenário.

Assim, se um sistema for desenvolvido sem que haja uma modelagem de banco de dados bem executada no início do projeto, as chances dele apresentar falhas ou até mesmo de não suprir os objetivos para os quais foi criado são grandes.

## PostgreSQL

Em uma reunião via discord a equipe discutiu e optou por usar o PostgreSQL como banco de dados da aplicação.
O postgreSQL é um sistema de gerenciamento de banco de dados relacional de objeto, ele suporta grande parte do padrão SQL e oferece muitos recursos.

## Metodologia

Os participantes se reuniram presencialmente e rascunharam um possível fluxo de dados, listaram os atributos e entidades necessárias a princípio para a modelagem do banco. 
No primeiro nível de abstração foi utilizado o modelo de entidade relacionamento para descrever as entidades, os atributos e como eles se relacionam entre si.
No segundo nível foi utilizado um diagrama de entidade-relacionamento que é um fluxograma para ilustrar entidades e como eles se relacionam, para finalmente chegar ao nível lógico, onde foi ilustrado as tabelas que o banco de dados deverá ter.
<br>
Para decidir em qual idioma o código do projeto será escrito, foi criada uma votação no nosso meio de comunicação mais rápido, o Telegram, e ficou decidido que todo o código será escrito em inglês, por esse motivo os atributos, entidades e relacionamentos estão em inglês.


## Participantes

- [Thais Rebouças](https://github.com/Thais-ra)
- [Yudi Yamane](https://github.com/yudi-azvd)

## Resultados

### Modelo Entidade-Relacionamento (ME-R)

### Entidades
- COURSE
- GRADUATION
- CURRICULUM

### Atributos

- COURSE(idCourse, courseName, courseDescription, courseCredits, courseWorkLoadInHours, preRequisites, coRequisites, equivalentTo)
- GRADUATION(idGraduation, name, description, credits, workInHours)
- CURRICULUM(idCurriculum, curriculumName, curriculumYear)

### Relacionamentos

- GRADUATION **have** CURRICULUM
<br>
Um curso(graduation) pode ter um ou mais currículos(curriculum) - relacionamento 1:n
Um currículo pode ser gerado apenas por um curso - relacionamento 1:1
<br>
Cardinalidade **1:n**

- CURRICULUM **contains** COURSE
Um currículo contém(contains) um ou várias disciplinas(course) - relacionamento 1:n
Uma disciplina está contida em um ou vários currículos - relacionamento 1:n
<br>
Cardinalidade **1:n**

### Diagrama Entidade-Relacionamento (DE-R)

<img src="images/Modelagem/diagramaConceitual.jpg" align = "center" />
<p align = "center"> 
Figura 1 - Diagrama Conceitual <br>
Autora: <a href="https://github.com/Thais-ra"> Thaís Rebouças </a> 
</p>

### Diagrama Lógico de Dados

<img src="images/Modelagem/diagramaLogico.jpg" align = "center" />
<p align = "center"> 
Figura 2 - Diagrama Lógico<br>
Autora: <a href="https://github.com/Thais-ra"> Thaís Rebouças </a> 
</p>

### Dicionário de Dados
<br>
<table>
<thead>
  <tr>
    <th colspan="5">Entidade: GRADUATION</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td colspan="5">Descrição: Curso de graduação</td>
  </tr>
  <tr>
    <td>Atributo</td>
    <td>Propriedades do atributo</td>
    <td>Tipo do dado</td>
    <td>Tamanho</td>
    <td>Descrição</td>
  </tr>
  <tr>
    <td>idGraduation</td>
    <td>primary key<br>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação do curso de graduação</td>
  </tr>
  <tr>
    <td>graduationName</td>
    <td>unique<br>not null</td>
    <td>string</td>
    <td>50</td>
    <td>Nome do curso de graduação</td>
  </tr>
  <tr>
    <td>graduationDescription</td>
    <td>-</td>
    <td>string</td>
    <td>100</td>
    <td> Descrição do curso</td>
  </tr>
  <tr>
    <td>graduationCredits</td>
    <td>not null</td>
    <td>integer</td>
    <td>-</td>
    <td>Créditos necessários para a formação</td>
  </tr>
  <tr>
    <td>graduationWorkInLoadInHours</td>
    <td>not null</td>
    <td>integer</td>
    <td>-</td>
    <td>Horas necessárias para a formação</td>
  </tr>
</tbody>
</table>

<br>

<table>
<thead>
  <tr>
    <th colspan="5">Entidade: CURRICULUM</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td colspan="5">Descrição: Matriz curricular</td>
  </tr>
  <tr>
    <td>Atributo</td>
    <td>Propriedades do atributo</td>
    <td>Tipo do dado</td>
    <td>Tamanho</td>
    <td>Descrição</td>
  </tr>
  <tr>
    <td>idCurriculum</td>
    <td>primary key<br>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação da matriz curricular</td>
  </tr>
  <tr>
    <td>curriculumName</td>
    <td>unique<br>not null</td>
    <td>string</td>
    <td>50</td>
    <td>Nome da matriz curricular</td>
  </tr>
  <tr>
    <td>curriculumYear</td>
    <td>not null</td>
    <td>string</td>
    <td>8</td>
    <td>Ano da matriz curricular</td>
  </tr>
  <tr>
    <td>idGraduation</td>
    <td>foreign key<br>not null</td>
    <td>string</td>
    <td>10</td>
    <td> Código de identificação da graduação relacionada à matriz curricular</td>
  </tr>
</tbody>
</table>

<br>

<table>
<thead>
  <tr>
    <th colspan="5">Relacionamento: contains</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td colspan="5">Descrição: Relaciona uma disciplina à matriz curricular a qual ela pertence</td>
  </tr>
  <tr>
    <td>Atributo</td>
    <td>Propriedades do atributo</td>
    <td>Tipo do dado</td>
    <td>Tamanho</td>
    <td>Descrição</td>
  </tr>
  <tr>
    <td>idCurriculum</td>
    <td>foreign key<br>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação da matriz curricular</td>
  </tr>
  <tr>
    <td>idCourse</td>
    <td>foreign key<br>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação da disciplina</td>
  </tr>
  <tr>
    <td>type</td>
    <td>not null</td>
    <td>enum</td>
    <td>-</td>
    <td>Tipo da disciplina quando associada<br>a matriz curricular, sendo: <br>OPT=optativa, <br>OBR=Obrigatória, <br>ML=Módulo livre e <br>CO=Complementar</td>
  </tr>
</tbody>
</table>

<br>

<table>
<thead>
  <tr>
    <th colspan="5">Entidade: COURSE</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td colspan="5">Descrição: Disciplinas necessárias para a conclusão de cursos de graduação</td>
  </tr>
  <tr>
    <td>Atributo</td>
    <td>Propriedades do atributo</td>
    <td>Tipo do dado</td>
    <td>Tamanho</td>
    <td>Descrição</td>
  </tr>
  <tr>
    <td>idCourse</td>
    <td>primary key<br>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação da disciplina</td>
  </tr>
  <tr>
    <td>courseName</td>
    <td>not null</td>
    <td>string</td>
    <td>50</td>
    <td>Nome da disciplina</td>
  </tr>
  <tr>
    <td>courseDescription</td>
    <td>-</td>
    <td>string</td>
    <td>100</td>
    <td> Descrição da disciplina</td>
  </tr>
  <tr>
    <td>courseCredits</td>
    <td>not null</td>
    <td>integer</td>
    <td>-</td>
    <td>Quantidade de créditos da disciplina</td>
  </tr>
  <tr>
    <td>courseWorkInLoadInHours</td>
    <td>not null</td>
    <td>integer</td>
    <td>-</td>
    <td>Quantidade de horas da disciplina</td>
  </tr>
</tbody>
</table>

<br>

<table>
<thead>
  <tr>
    <th colspan="5">Relacionamento: preRequisites</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td colspan="5">Descrição: Pré-requisitos necessários para cursar uma disciplina</td>
  </tr>
  <tr>
    <td>Atributo</td>
    <td>Propriedades do atributo</td>
    <td>Tipo do dado</td>
    <td>Tamanho</td>
    <td>Descrição</td>
  </tr>
  <tr>
    <td>idPreRequisites</td>
    <td>primary key<br>not null</td>
    <td>integer</td>
    <td>-</td>
    <td>Código de identificação do relacionamento entre o pré-requisito e a disciplina</td>
  </tr>
  <tr>
    <td>idCourse</td>
    <td>foreign key<br>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação da disciplina relacionada ao pré-requisito </td>
  </tr>
  <tr>
    <td>preRequisite</td>
    <td>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação da disciplina que é pré-requisito</td>
  </tr>
</tbody>
</table>

<br>

<table>
<thead>
  <tr>
    <th colspan="5">Relacionamento: coRequisites</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td colspan="5">Descrição: Có-requisitos necessários para cursar uma disciplina</td>
  </tr>
  <tr>
    <td>Atributo</td>
    <td>Propriedades do atributo</td>
    <td>Tipo do dado</td>
    <td>Tamanho</td>
    <td>Descrição</td>
  </tr>
  <tr>
    <td>idCoRequisites</td>
    <td>primary key<br>not null</td>
    <td>integer</td>
    <td>-</td>
    <td>Código de identificação do relacionamento entre o co-requisito e a disciplina</td>
  </tr>
  <tr>
    <td>idCourse</td>
    <td>foreign key<br>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação da disciplina relacionada ao co-requisito </td>
  </tr>
  <tr>
    <td>coRequisite</td>
    <td>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação da disciplina que é co-requisito</td>
  </tr>
</tbody>
</table>

<br>

<table>
<thead>
  <tr>
    <th colspan="5">Relacionamento: equivalentTo</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td colspan="5">Descrição: Disciplinas equivalentes</td>
  </tr>
  <tr>
    <td>Atributo</td>
    <td>Propriedades do atributo</td>
    <td>Tipo do dado</td>
    <td>Tamanho</td>
    <td>Descrição</td>
  </tr>
  <tr>
    <td>IdEquivalentTo</td>
    <td>primary key<br>not null</td>
    <td>integer</td>
    <td>-</td>
    <td>Código de identificação do relacionamento entre a disciplina equivalente e a disciplina em questão</td>
  </tr>
  <tr>
    <td>idCourse</td>
    <td>foreign key<br>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação da disciplina relacionada à equivalencia</td>
  </tr>
  <tr>
    <td>equivatentTo</td>
    <td>not null</td>
    <td>string</td>
    <td>10</td>
    <td>Código de identificação da disciplina que é equivalente</td>
  </tr>
</tbody>
</table>
<br>

## Referências

o que é um diagrama entidade relacionamento?, Lucidchart. Disponível em: https://www.lucidchart.com/pages/pt/o-que-e-diagrama-entidade-relacionamento. Acesso em: 14 de julho de 2022.

O que é a modelagem de banco de dados e quais os seus principais conceitos, Escola superior de redes. Disponível em: https://esr.rnp.br/desenvolvimento-de-sistemas/open-5/. Acesso em: 14 de julho de 2022.

Documentation PostgreSQL 14, PostgreSQL. Disponível em: https://www.postgresql.org/docs/current/intro-whatis.html. Acesso em: 14 de julho de 2022.

MER e DER: Modelagem de bancos de dados, DevMedia. Disponível em: https://www.devmedia.com.br/mer-e-der-modelagem-de-bancos-de-dados/14332. Acesso em: 14 de julho de 2022.
