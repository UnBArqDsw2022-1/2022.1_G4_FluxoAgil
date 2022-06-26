# Políticas de Branch

## Histórico de versões
| Data     | Versão | Descrição            | Autor(a)                                      | Revisor(a)                                       |
| -------- | ------ | -------------------- | --------------------------------------------- | ------------------------------------------------ |
| 19.06.22 | 1.0    | Criação do documento | [Thaís Rebouças](https://github.com/Thais-ra) | [Matheus Fonseca](https://github.com/gatotabaco) |

## Introdução

As políticas de branch são uma parte importante do fluxo de trabalho do Git e permite aos contribuidores isolarem o trabalho em andamento do trabalho já concluído na main, e um maior controle do que será colocado em produção.


## Branches Padrão
### Main
A branch main representa uma versão estável do produto, contendo código já testado, pronto para ser entregue ao usuário final ou cliente. Essa branch parte da branch dev através de pull requests aprovados e revisados.

    Regras:
        Existe apenas uma branch main.
        Não são permitidos commits feitos diretamente nela.

### Dev
A branch dev contém a versão mais atualizada do código que está sendo desenvolvido. Essa branch está sempre sincronizada com a main e é base para as branches feature.

    Regras:
        Existe apenas uma branch dev.
        Essa branch está sempre sincronizada com a branch main.

## Branches de Desenvolvimento
### Feature
As branches feature representam as funcionalidades do sistema a serem desenvolvidas, elas devem ter a branch dev como sua origem e fim.

    Regras:
        Essa branch sempre é criada a partir da branch dev.
        Essa branch sempre é mesclada à branch dev.

    Regras de nomenclatura:
        issueID-feature/titulo-da-issue

### Hotfix
A branch hotfix é utilizada para implementar soluções para problemas urgentes encontrados no ambiente de produção. Isso significa que essa branch deve ter a branch main como sua origem e fim.

    Regras:
        Essa branch sempre é criada a partir da branch main.
        Essa branch sempre é mesclada à branch main e a dev.

    Regras de nomenclatura:
        issueID-hotfix/titulo-da-issue

## Documentation
A branch documentation é utilizada para atualizações na documentação de todo o projeto. Essa branch deve ter a branch main como sua origem e fim.

    Regras:
        Essa branch sempre é criada a partir da branch main.
        Essa branch sempre é mesclada à branch main.

    Regras de nomenclatura:
        issueID-documentation/titulo-da-issue


## Referências

Deepsource. Git branch naming conventions. Disponível em: https://deepsource.io/blog/git-branch-naming-conventions/. Acesso em: 19 de junho de 2022.

Tableless. Gerenciando seus branches com o Git Flow. Disponível em: https://tableless.com.br/git-flow-introducao/. Acesso em: 19 de junho de 2022.

2019.2-Acacia. Políticas do Repositório. Disponível em: https://github.com/fga-eps-mds/2019.2-Acacia/blob/develop/docs/policies.md. Acesso em: 19 de junho de 2022.