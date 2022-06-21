# Política de commit

## Visão geral

A política de commits desse projeto é baseada no 
[Conventional Commits v1.0.0](https://www.conventionalcommits.org/pt-br/v1.0.0/). 
Conventional Commits define um conjunto de regras simples para que as mensagens
commit sejam consistentes no histórico de um repositório. Utilizar uma convenção
como essa facilita a leitura do histórico, a identificação das mudanças 
realizadas por um commit e facilita a adoção de ferramentas de automação para 
gerar changelogs ou release notes.

Além disso, Conventional Commits também é compatível com a convenção de 
[versionamento semântico](https://semver.org/lang/pt-BR/).

A estrutura de um commit é a seguinte:

```
<tipo>[escopo opcional]: <descrição>

[corpo opcional]

[rodapé(s) opcional(is)]
```

O commit contém os seguintes elementos estruturais, para comunicar a intenção 
ao utilizador da sua biblioteca:

1. **fix**: um commit do tipo fix soluciona um problema na sua base de código (isso 
se correlaciona com PATCH do versionamento semântico).
1. **feat**: um commit do tipo feat inclui um novo recurso na sua base de código 
(isso se correlaciona com MINOR do versionamento semântico).
1. **BREAKING CHANGE**: um commit que contém no rodapé opcional o texto `BREAKING CHANGE:`,
ou contém o símbolo `!` depois do tipo/escopo, introduz uma modificação que quebra a 
compatibilidade da API (isso se correlaciona com MAJOR do versionamento semântico). 
Uma BREAKING CHANGE pode fazer parte de commits de qualquer _tipo_.
1. Outros tipos adicionais são permitidos além de `fix:` e `feat:`, por exemplo 
[@commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional)
(baseado na 
[Convenção do Angular](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines))
recomenda-se `build:`, `chore:`, `ci:`, `docs:`, `style:`, `refactor:`, `perf:`,
`test:`, entre outros. Outros rodapés diferentes de BREAKING CHANGE: `<descrição>`
podem ser providos e seguem a convenção simular a git trailer format.

Essa política de commits será utilizada em todos os repositórios do projeto
Fluxo Ágil.

## Mais informações
Para mais informações e exemplos, confira o 
[documento original v1.0.0](./conventional-commits-original.md).

## Referências

[Commits Convencionais](https://www.conventionalcommits.org/pt-br/v1.0.0/)
