# GoF: Strategy Pattern

## Histórico de versões
| Data       | Versão | Descrição                            | Autor(a)                                                                             | Revisor(a) |
| ---------- | ------ | ------------------------------------ | ------------------------------------------------------------------------------------ | ---------- |
| 10/08/2022 | 0.1    | Criação do rascunho com a intrução   | [Matheus Sousa](https://github.com/gatotabaco), [Thaís](https://github.com/Thais-ra) |            |
| 12/08/2022 | 0.2    | Alteração na introdução e referência | [Matheus Sousa](https://github.com/gatotabaco), [Thaís](https://github.com/Thais-ra) |            |

## Introdução

O State é um padrão de projeto comportamental que permite que um objeto altere seu comportamento quando seu estado interno muda, como se o objeto mudasse de classe. 
O padrão State sugere que você crie novas classes para todos os estados possíveis de um objeto e extraia todos os comportamentos específicos de estados para dentro dessas classes.

Ao invés de implementar todos os comportamentos por conta própria, o objeto original, chamado contexto, armazena uma referência para um dos objetos de estado que representa seu estado atual, e delega todo o trabalho relacionado aos estados para aquele objeto.
As partes que mais aparecem quando esse padrão é implementado são:

- **Contexto**: Armazena uma referência a um dos objetos concretos de estado e delega a eles todos os trabalhos específicos de estado. O contexto se comunica com o objeto estado através da interface do estado. O contexto expõe um setter para passar a ele um novo objeto de estado.
- **Estado**: Declara métodos específicos a estados. Esses métodos devem fazer sentido para todos os estados concretos para não terem estados com métodos que nunca irão ser chamados.
- **Estados concretos**: Fornecem suas próprias implementações para os métodos específicos de estados. Para evitar duplicação ou 
código parecido em múltiplos estados, você pode fornecer classes abstratas intermediárias que encapsulam alguns dos comportamentos comuns.

Objetos de estado podem armazenar referências retroativas para o objeto de contexto. Através dessa referência o estado pode buscar qualquer 
informação desejada do objeto contexto, assim como iniciar transições de estado.

## Metodologia

Os participantes se reuniram via discord para discutir em qual parte do projeto seria necessário utilizar o padrão comportamental state, e chegaram na conclusão de que não será aplicado. Então os exemplos que se seguem não se encaixam no contexto do projeto e são ilustrativos.

## Participantes

- [Matheus Sousa](https://github.com/gatotabaco)
- [Thaís Rebouças](https://github.com/Thais-ra)

## Resultados

<p align="center">
    <img src="images/padroes-projeto/gofs-state.png"/>
</p>
<p align = "center"> 
Figura 1 - Diagrama ilustrando a ideia do padrão de estado.<br>
Fonte: Matheus Sousa e Thaís Rebouças
</p>

### Exemplo de código


## Referências

State. Refactoring Guru, Elements of Reusable Object-Oriented Software. Disponível em: https://refactoring.guru/pt-br/design-patterns/state. Acesso em: 12 de agosto de 2022.
