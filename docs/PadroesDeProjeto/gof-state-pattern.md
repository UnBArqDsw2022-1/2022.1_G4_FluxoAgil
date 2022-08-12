# GoF: Strategy Pattern

## Histórico de versões
| Data       | Versão | Descrição                            | Autor(a)                                                                             | Revisor(a) |
| ---------- | ------ | ------------------------------------ | ------------------------------------------------------------------------------------ | ---------- |
| 10/08/2022 | 0.1    | Criação do rascunho com a intrução   | [Matheus Sousa](https://github.com/gatotabaco), [Thaís](https://github.com/Thais-ra) |       -     |
| 12/08/2022 | 0.2    | Alteração na introdução e referência | [Matheus Sousa](https://github.com/gatotabaco), [Thaís](https://github.com/Thais-ra) |      -      |
| 12/08/2022 | 0.3    | Adiciona exemplo de código, referência e diagrama | [Matheus Sousa](https://github.com/gatotabaco), [Thaís](https://github.com/Thais-ra) | - | 
| 12/08/2022 | 1.0    | Adiciona versão final do documento | [Matheus Sousa](https://github.com/gatotabaco), [Thaís](https://github.com/Thais-ra) | [Amanda Nobre](https://github.com/AmandaNbr) | 

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

Os participantes se reuniram via discord para discutir em qual parte do projeto seria necessário utilizar o padrão comportamental state, e chegaram na conclusão de que não será aplicado. Então, foi utilizado um exemplo baseado em uma situação-problema hipotética, referente a uma classe student, que pode ser um estudante em três condições distintas: calouro (não pode escolher as matérias da matrícula), graduando (faz a matricula em disciplinas), e graduado (não pode se matricular).

Em cada um desses estados, o processo de matrícula vai funcionar de modo diferente:

- Calouro: Ao se matricular, recebe as disciplinas estáticas que irá custar automaticamente.
- Graduando: Escolhe individualmente as disciplinas que irá cursar, e então é matriculado nelas.
- Graduado: Não acontecerá nada, pois quem está graduado não pode se matricular em disciplinas.

A partir desse contexto pré definido, foi elaborado um diagrama de classes, que será abordado posteriormente neste documento, para demonstrar a estrutura do nosso código exemplo.

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

As classes seriam implementadas da seguinte forma:

`Student`
```
class Student is
    field state: State
    
    constructor student(state: Freshman) is
        this.state = new changeState(state)
        
    method changeState(state: State) is
        this.state = state
        
    method enrollSubject() is
        state.enrollSubject()
    method withdrawDiscipline() is
        state.withdrawDiscipline()
```

`State`
```
abstract class State is
    protected field state: Student
    
    constructor State(state) is
        this.state = state
        
    abstract method enrollSubject()
    abstract method withdrawDiscipline()
    
```

`Freshman`
```
class Freshman extends State is
    method enrollSubject() is
        // automatic enrollment in the standard freshman subjects
        state.changeState(new Graduating(state))
        
    method withdrawDiscipline() is
        // nothing happends, freshman cant withdraw disciplines
```

`Graduating`
```
class Graduating extends State is
    method enrollSubject() is
        // choose the subjects to enroll and sucessfully enroll them
        
    method withdrawDiscipline() is
        // choose the subjects to wirhdraw then sucessfully withdraw them

```

`Graduated`
```
class Graduated extends State is
    method enrollSubject() is
        // nothing happens. Graduated students cant  enroll
        
    method withdrawDiscipline() is
        // nothing happends. Graduated students cant withdraw any subjects

```

## Referências

State. Refactoring Guru, Elements of Reusable Object-Oriented Software. Disponível em: https://refactoring.guru/pt-br/design-patterns/state. Acesso em: 12 de agosto de 2022.

Design Patterns - State Pattern. Disponível em: https://www.tutorialspoint.com/design_pattern/state_pattern.htm#. Acesso em: 12 de agosto de 2022.
