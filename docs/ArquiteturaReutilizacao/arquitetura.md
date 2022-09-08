# Documento de Arquitetura de Software

## Histórico de versões
| Data       | Versão | Descrição            | Autor(a)                                    | Revisor(a)                                    |
| ---------- | ------ | -------------------- | ------------------------------------------- | --------------------------------------------- |
| 05/09/2022 | 0.1    | Criação do documento | [Yudi Yamane](https://github.com/yudi-azvd) | [Thaís Rebouças](https://github.com/Thais-ra) |

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

- ter seu dispositivo conectado à internet

- ter um navegador instalado no dispositivo móvel ou computador

- ter acesso ao SIGAA e ser aluno da UnB


### Metas

A metas para o Fluxo Ágil são:

- Usabilidade: fácil e simples de usar para gerar a recomendação de fluxo

- Responsividade: deve funcionar no celular e no desktop


## Lógica
...

## Implantação
...

## Implementação
...

## Dados
...


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
