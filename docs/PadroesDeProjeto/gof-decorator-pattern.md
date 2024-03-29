# GoF: Decorator Pattern

## Histórico de versões

| Data       | Versão | Descrição            | Autor(a)                                                    | Revisor(a)                                       |
| ---------- | ------ | -------------------- | ----------------------------------------------------------- | ------------------------------------------------ |
| 11/08/2022 | 1.0    | Criação do documento | [matheusyanmonteiro](https://github.com/matheusyanmonteiro) | [Mateus Maia](https://github.com/mateusmaiamaia) |

## Introdução

O padrão decorator é um dos padrões estruturais amplamente utilizados. Esse padrão altera dinamicamente a funcionalidade de um objeto em tempo de execução sem afetar a funcionalidade existente dos objetos. Em resumo, este padrão adiciona funcionalidades adicionais ao objeto envolvendo-o.

## Metodologia

Decorator Design:

- Componente – este é o wrapper que pode ter responsabilidades adicionais associadas a ele em tempo de execução.
- Componente de concreto- é o objeto original ao qual as funcionalidades adicionais são adicionadas.
- Decorator-esta é uma classe abstrata que contém uma referência ao objeto componente e também implementa a interface do componente.

## Participantes

- [matheusyanmonteiro](https://github.com/matheusyanmonteiro)

## Exemplo

No nosso projeto o padrão decorator será amplamente utilizado na parte de front end com o react. O conceito de componentização e de spa faz uso constante de objetos que sempre modificação de estado mas sem perder as caracteristicas iniciais.

Para exemplificar apresentaremos um codigo com comentarios de como funciona um decorator em typescript.

```ts
/**
 * A interface Component base define operações que podem ser alteradas por
 */
interface Component {
  operation(): string;
}

/**
 * Componentes Concretos fornecem implementações padrão das operações. aqui
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
 * decoradores de concreto. A implementação padrão do código de encapsulamento pode facilitar a visualização de como o codigo sera reutilizado
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
   * chamar o objeto encapsulado diretamente. Esta abordagem simplifica a extensão
   * das classes de decorador.
   */
  public operation(): string {
    return `ConcreteDecoratorA(${super.operation()})`;
  }
}

/**
 * Decorators podem executar seu comportamento antes ou depois da chamada para um
 * objeto encapsulado.
 */
class ConcreteDecoratorB extends Decorator {
  public operation(): string {
    return `ConcreteDecoratorB(${super.operation()})`;
  }
}

/**
 * O código cliente funciona com todos os objetos usando a interface Component. Desta maneira que podendo ser independente das classes concretas de componentes.
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

Referência: DESIGN Pattern. Disponível em: https://refactoring.guru/design-patterns/decorator/typescript/example. Acesso em: 11 ago. 2022.

Referência: DECORATOR GoFs. Disponível em: https://dzone.com/articles/gang-four-%E2%80%93-decorate-decorator. Acesso em: 11 ago. 2022.
