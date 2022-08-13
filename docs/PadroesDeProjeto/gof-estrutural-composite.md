# GoF: Composite Pattern

## Histórico de versões

| Data       | Versão | Descrição            | Autor(a)                                                                   | Revisor(a)                               |
| ---------- | ------ | -------------------- | -------------------------------------------------------------------------- | ---------------------------------------- |
| 11/08/2022 | 1.0    | Criação do documento | [Lucas Braun](https://github.com/lbvx) | [Matheus Pinheiro](https://github.com/matheuscvp) |

## Introdução

O padrão estrutural Composite permite que objetos sejam criados em estruturas de árvore, mas de forma que as composições de objetos e os objetos individuais possam ser tratados de maneira uniforme. Para obtermos esse comportamento, é usado uma classe abstrata que representa tanto as composições quanto os objetos individuais.

<p align="center">
    <img src="images/padroes-projeto/gofs-composite.png"/>
</p>
<p align = "center"> 
Figura 1 - Diagrama ilustrando padrão composite<br>
Fonte: GAMMA, Erich et al.
</p>

## Metodologia

### Exemplo de interface em python

Já que Python suporta herança múltipla, não há necessidade da existência de interfaces na linguagem, mas não significa que não há uso para elas. Portanto, existem bibliotecas da própria linguagem, como a abc (abstract base classes), que nos permite controlar melhor a criação e uso de classes abstratas.

```python
# ABC = Abstract Base Class
# faz com que não seja permitido instanciar um objeto da classe
from abc import ABC, abstractmethod

# Classe abstrata
class Poligono(ABC):
    @abstractmethod
    def n_lados(self):
        pass

class Quadrado(Poligono):
    def n_lados(self):
        return 4

class Triangulo(Poligono):
    def n_lados(self):
        return 3

class Hexagono(Poligono):
    def n_lados(self):
        return 6

p = Triangulo()
n = p.n_lados()

```

## Participantes

- [Lucas Braun](https://github.com/lbvx)

## Resultados

### Exemplo de código no contexto do projeto

As classes Curriculum e Course possuem uma relação de composição, de forma que as carga horária de um currículo é igual a soma das cargas horárias dos cursos associadas. Podemos implementar o padrão Composite nessa relação da seguinte forma:

```python
from abc import ABC, abstractmethod

# Interface para o calculo de carga horario que sera implementada pelas duas classes relacionadas
class WLInterface(ABC):
    @abstractmethod
    def get_workload(self):
        pass

class Curriculum(WLInterface):
    def get_workload(self):
        return sum((c.get_workload() for c in self.courses))

class Course(WLInterface):
    def get_workload(self):
        return self.workload

```

## Referências

GAMMA, Erich et al. Design patterns: elements of reusable object-oriented software. Pearson Deutschland GmbH, 1995

DESIGN Pattern. Disponível em: https://refactoring.guru/design-patterns/composite. Acesso em: 11/08/2022.