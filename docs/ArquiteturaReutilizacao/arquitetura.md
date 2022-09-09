# Documento de Arquitetura de Software

## Histórico de versões
| Data       | Versão | Descrição                                        | Autor(a)                                     | Revisor(a)                                    |
| ---------- | ------ | ------------------------------------------------ | -------------------------------------------- | --------------------------------------------- |
| 05/09/2022 | 1.0    | Criação do documento                             | [Yudi Yamane](https://github.com/yudi-azvd)  | [Thaís Rebouças](https://github.com/Thais-ra) |
| 08/09/2022 | 1.1    | Adição da Visão de Casos de Uso e de Implantação | [Amanda Nobre](https://github.com/AmandaNbr) | [Yudi Yamane](https://github.com/yudi-azvd)   |

## Introdução

Este documento apresenta as decisões sobre arquitetura e ferramentas tomadas durante o 
desenvolvimento do projeto **Fluxo Ágil**.

## Visão geral

Segue a visão geral da arquitetura da aplicação Fluxo Ágil.

<p align="center"> <img alt="Arquiterura: visão geral" 
  src="images/arquitetura/arq-geral.png"/> </p>
<p align="center">
Figura 1 - Arquiterura: visão geral<br>
Fonte: Diagrams.net
</p>


Em seguida, as principais ferramentas utilizadads são explicadas brevemente.

### Server

**Flask**  é um micro framework backend para Python para desenvolver aplicações
web baseadas em templates. Sem pouco rígido, oferece ao desenvolvedor a liberdade
des escolher outras extensões a bibliotecas para desenvolver o seu projeto.  
**Flask RESTful** é uma extensão para Flask para transformá-lo em framework para
APIs REST (semelhante ao Django REST para o Django).

**Docker** é uma plataforma com um conjunto de ferramentas que permite isolar a
aplicação do ambiente de execução, de maneira que resolva o clássico problema do
"mas na minha máquina funciona". Com Docker é possível gerenciar a infraestrutra
tão facilmente quanto a aplicação em si e diminuir a diferença entre ambiente
de desenvolvimento e produção. 

**SQLAlchemy** atua como ORM para a camada de dados do backend. É responsável 
por abstrair as queries em SQL em chamadas de funções em cima dos modelos 
definidos no projeto, além de estabelecer a conexão com o banco de dados. 

**PostgreSQL** é um sistema gerenciador de banco de dados relacional open 
source. É o banco com o qual o SQLAlchemy de fato se comunica. É complacente com 
o padrão ACID, tem suporte para vários sistemas operacionais e linguagens 
procedurais e tem o SQL como linguagem de query.


### Web
 
**React** é um biblioteca JavaScript para construção de interfaces de usuário na 
web.
É baseada em componentes, o que facilita a reutilização e separação da lógica
de cada um deles para construir interfaces complexas. Além disso, segue um padrão declarativo, no qual o desenvolvedor
expressa _o que_ o vai aparecer na interface em vez de _como_ deve aparecer na 
interface.

**Redux Toolkit**

**Material UI** foi a biblioteca escolhida como biblioteca de estilo. É baseada
no Material Design do Google e é open source.


## Participantes

- [Amanda Nobre](https://github.com/AmandaNbr)
- [Matheus Calixto](https://github.com/matheuscvp)
- [Yudi Yamane](https://github.com/yudi-azvd)

## Restrições e Metas de Arquitetura

### Restrições
O usuário precisa:

- Ter o dispositivo conectado à internet.

- Ter um navegador instalado no dispositivo móvel ou computador.

- Ter acesso ao SIGAA e ser aluno da UnB.


### Metas
A metas para o Fluxo Ágil são:

- Usabilidade: fácil e simples de usar para gerar a recomendação de fluxo.

- Responsividade: deve funcionar no celular e no desktop.

## Visão de Casos de Uso

A Visão de Casos de Uso descreve um modelo com alta significância de alto nível em relação às funcionalidades do sistema  e normalmente é representado através do Diagrama de Casos de Uso. Como o projeto tem um escopo bastante restrito de funcionalidades, há a possibilidade de, no contexto do Fluxo Ágil, representar a Visão de Casos de Uso com outro artefato que também demonstre com clareza as funcionalidades da aplicação.

O Rich Picture é uma ferramenta que possibilita a identificação de funcionalidades, atores, relacionamentos e responsabilidades dos atores com os processos.

<p align = "center"> <img alt="richpicture10" src="images/rich_picture/rich_picture_final.jpg" height="500px" width="800px" /> </p>
<p align = "center"> 
Figura - Rich Picture final <br>
Autores: <a href="https://github.com/lbvx">Lucas Braun</a> e <a href="https://github.com/mateusmaiamaia">Mateus Maia</a>
</p>

Também é possível observar a funcionalidade do sistema a partir dos storyboards:

<img src="images/storyboard/storyboard1.png" align = "center" />
<p align = "center"> 
Figura - Storyboard 1 <br>
Autor: Matheus Pinheiro
</p>

<img src="images/storyboard/storyboard2.jpg" align = "center" />
<p align = "center"> 
Figura - Storyboard 2 <br>
Autor: Matheus Pinheiro
</p>

## Visão Lógica
<!-- Diagrama de classe e Pacotes -->

## Visão de Implantação

A Visão de Implantação diz respeito a explicitar, de forma clara, como os componentes e processos se relacionam e dependem entre si. É representada a partir de uma modelagem da arquitetura física do sistema, normalmente através de um Diagrama de Implantação.

<p align = "center"> <img src="images/diagramas/diagramaImplantacao.png" /> </p>
<p align = "center"> 
Figura - Diagrama de Implantação <br>
Autoras: Amanda Nobre e Ana Carolina</a> 
</p>

O diagrama acima possui representações das camadas da aplicação Fluxo Ágil, que consistem em Backend e Frontend, como application server, e a interface que o usuário tem acesso, sendo client server. Esse usuário se comunica com a aplicação por meio de um browser no qual o frontend está hospedado. A partir de requisições o frontend se comunica com o backend da aplicação, que por sua vez tem acesso ao banco de dados, onde as informações persistentes são colhidas através de uma raspagem de dados. 

## Visão de Implementação
<!-- A Visão de Implementação procura mostrar como o sistema será desenvolvido e organizado. Pode-se então utilizar o Diagrama de Componetes para tal demonstração. -->

## Visão de Dados

<!-- A visão de Dados é um tópico que se dispõe a mostrar quais são os dados persistentes na aplicação, geralmente utiliza-se ferramentas como um Modelo Entidade-Relacionamento e/ou Diagrama Entidade-Relacionamento para isso -->


## Referências

<!-- https://referenciabibliografica.net/a/pt-br/ref/abnt -->

FLASK: Web development. In: Flask. [S. l.], 4 jan. 2010. Disponível em: https://en.wikipedia.org/wiki/Flask_(web_framework). Acesso em: 4 set. 2022.

Get Started with Docker. Disponível em 
https://docs.docker.com/gettarted/overview/. Acesso em: 4 set. 2022.

SQLAlchemy: The Python SQL Toolkit and Object Relational Mapper
https://www.sqlalchemy.org/. Acesso em: 4 set. 2022.

Postgres: About. https://www.postgresql.org/about/. Acesso em: 4 set. 2022.

ReactJS. https://reactjs.org/. Acesso em: 7 set. 2022.

Redux Toolkit. https://redux-toolkit.js.org/. Acesso em: 7 set. 2022.

Stock. https://unbarqdsw.github.io/2020.1_G12_Stock/#/.  Acesso em: 8 set. 2022.