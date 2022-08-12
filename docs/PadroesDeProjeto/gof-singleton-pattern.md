# GoF: Strategy Pattern

## Histórico de versões

| Data       | Versão | Descrição            | Autor(a)                                                    | Revisor(a)                               |
| ---------- | ------ | -------------------- | ----------------------------------------------------------- | ---------------------------------------- |
| 11/08/2022 | 1.0    | Criação do documento | [Mateus Maia](https://github.com/mateusmaiamaia) | [Matheus Calixto](https://github.com/matheuscvp) |
| 12/08/2022 | 1.0    | Correção de de erros pontuais no documento | [Mateus Maia](https://github.com/mateusmaiamaia) | [Matheus Calixto](https://github.com/matheuscvp) |

## Introdução

O singleton é um padrão de projeto que garante que haja somente uma intância de uma classe, ao mesmo tempo garante um acesso global para essa instância, tendo assim somente um ponto de acesso central a essa instancia da classe. O Singleton é bastante útil em duas situações, a primeira é quando existe a necessidade de controlar a concorrência de acesso a recursos compartilhados e a segunda é quando uma classe for utilizada com uma certa requência em várias partes do sistema.

## Metodologia

Uma possível aplicação do singleton no nosso projeto é relação a conexões do banco de dados, ela pode ser responsável pela gerência de criação, tempo de vida e distribuição de todas as conexões do banco de dados para o aplicativo, fazendo com que nenhuma conexão seja perdida. 

## Participantes

- [Mateus Maia](https://github.com/mateusmaiamaia)

### Exemplo de código

```ts
class  Database:

    __instance = None

    @staticmethod
    def getInstance():
        if Database.__instance == None:
            Datatabase.__instance = Database()
        return Database.__instance

    def __init__(self):
    if Database.__instance != None:
        raise Exception("Database object already created")
    else:
        Database.__instance = self

```

Este código não foi implementado, ele servirar como base para a criação do banco de dados do scraper, que será utilizado para pegar os dados das disciplinas dos cursos da Universidade de Brasília.

## Referências

DESIGN Patterns: Elements of Reusable Object-Oriented Software. [S. l.: s. n.], 1994.

https://www.opus-software.com.br/singleton-design-pattern/

https://refactoring.guru/pt-br/design-patterns/singleton
