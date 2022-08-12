# GoF: Strategy Pattern

## Histórico de versões

| Data       | Versão | Descrição            | Autor(a)                                                    | Revisor(a)                               |
| ---------- | ------ | -------------------- | ----------------------------------------------------------- | ---------------------------------------- |
| 11/08/2022 | 1.0    | Criação do documento | [matheusyanmonteiro](https://github.com/matheusyanmonteiro) | [Irwin](https://github.com/irwinschmitt) |

## Introdução

O padrão decorador é um dos padrões estruturais amplamente utilizados. Esse padrão altera dinamicamente a funcionalidade de um objeto em tempo de execução sem afetar a funcionalidade existente dos objetos. Em resumo, este padrão adiciona funcionalidades adicionais ao objeto envolvendo-o.

## Metodologia

Decorator Design:

- Componente – este é o wrapper que pode ter responsabilidades adicionais associadas a ele em tempo de execução.
- Componente de concreto- é o objeto original ao qual as funcionalidades adicionais são adicionadas.
- Decorator-esta é uma classe abstrata que contém uma referência ao objeto componente e também implementa a interface do componente.

## Participantes

- [matheusyanmonteiro](https://github.com/matheusyanmonteiro)

## Resultados

No nosso projeto o padrão decorator será amplamente utilizado na parte de front end com o react. O conceito de componentização e de spa faz uso constante de objetos que sempre modificação de estado mas sem perder as caracteristicas iniciais.

Para exemplificar apresentaremos um codigo com comentarios de como usar de como funciona um decorator em typescript.

### Exemplo de código

```ts
/**
 * A interface Component base define operações que podem ser alteradas por
 */
interface Component {
  operation(): string;
}

/**
 * Componentes Concretos fornecem implementações padrão das operações. Lá
 * podem ser várias variações dessas classes.
 */
class ConcreteComponent implements Component {
  public operation(): string {
    return 'ConcreteComponent';
  }
}

/**
 * A classe base Decorator segue a mesma interface dos demais componentes.
 * O objetivo principal desta classe é definir a interface de encapsulamento para todos
 * decoradores de concreto. A implementação padrão do código de encapsulamento pode
 * inclua um campo para armazenar um componente encapsulado e os meios para inicializar
 * isto.
 */

class Decorator implements Component {
  protected component: Component;

  constructor(component: Component) {
    this.component = component;
  }
  public operation(): string {
    return this.component.operation();
  }
}

/**
 * Concrete Decorators chamam o objeto encapsulado e alteram seu resultado de alguma forma.
 */
class ConcreteDecoratorA extends Decorator {
  /**
   * decoractors podem chamar a implementação pai da operação, em vez de
   * chamando o objeto encapsulado diretamente. Esta abordagem simplifica a extensão
   * das classes de decorador.
   */
  public operation(): string {
    return `ConcreteDecoratorA(${super.operation()})`;
  }
}

/**
 * Decoradores podem executar seu comportamento antes ou depois da chamada para um
 * objeto embrulhado.
 */
class ConcreteDecoratorB extends Decorator {
  public operation(): string {
    return `ConcreteDecoratorB(${super.operation()})`;
  }
}

/**
 * O código cliente funciona com todos os objetos usando a interface Component.  desta maneira que pode ficar independente das classes concretas de componentes.
 *
 */
function clientCode(component: Component) {
  // ...

  console.log(`RESULT: ${component.operation()}`);

  // ...
}

/**
 * Desta forma, o código do cliente pode suportar componentes simples...
 */
const simple = new ConcreteComponent();
console.log("Client: I've got a simple component:");
clientCode(simple);
console.log('');

/**
 * ...bem como os decorators.
 *
 * Observe como os decorators podem envolver não apenas componentes simples, mas os outros
 * decorators também.
 */
const decorator1 = new ConcreteDecoratorA(simple);
const decorator2 = new ConcreteDecoratorB(decorator1);
console.log("Client: Now I've got a decorated component:");
clientCode(decorator2);
```

## Referências
