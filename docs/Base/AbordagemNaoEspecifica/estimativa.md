# Estimativa de Esforço e de Tempo

## Histórico de versões
| Data     | Versão | Descrição            | Autor(a)                               | Revisor(a)                                  |
| -------- | ------ | -------------------- | -------------------------------------- | ------------------------------------------- |
| 25/06/22 | 1.0    | Criação do documento | [Lucas Braun](https://github.com/lbvx) | [Yudi Yamane](https://github.com/yudi-azvd) |

## Introdução

Este documento aborda a técnica utilizada para a estimativa de custos de esforço e tempo na fabricação do software. Estimativas são geralmente feitas nas fases iniciais do ciclo de vida de um projeto, pois ajudam na administração correta de recursos ao longo do tempo. Segundo Roetzheim (2000b), o uso de técnicas formais de estimativa pode dobrar a probabilidade do projeto ser concluído com sucesso. Existem diversos modelos de estimativas para projetos de software, e o utilizado nesse projeto será o COCOMO.

## Metodologia

### COCOMO

O Modelo de Custo Construtivo, ou COCOMO, é um modelo usado para estimar o tempo de desenvolvimento de um software criado por Barry Boehm. Teve de base um estudo sobre dezenas de projetos com escopos variados e grande diversidade de linguagens de programação e, portanto, pode ser útil para quase todos projetos de software. Dependendo do escopo do projeto e do nível de detalhes desejado no resultado, o COCOMO pode ser implementado de 3 modos:

- **COCOMO Básico**: mede o esforço e custo de desenvolvimento baseado em estimativa do tamanho do programa (linhas de código).
- **COCOMO Intermediário:** além de utilizar o tamanho do programa, também usa um conjunto de direcionadores de custo (avaliações subjetivas do produto, do hardware, do pessoal e dos atributos do projeto).
- **COCOMO Detalhado:** além das métricas do nível intermediário, inclui uma avaliação do impacto dos direcionadores de custo sobre cada etapa do desenvolvimento.

Além disso, o COCOMO pode ser aplicado em três classes de projetos:

- **Modo Orgânico:** para projetos simples, relativamente pequenos, e com requisitos não tão rígidos.
- **Modo Semidestacado**: para projetos intermediários em tamanho e complexidade, com alguns requisitos rígidos, e com níveis mistos de experiência nas equipes.
- **Modo Embutido**: para projetos com rígidas restrições operacionais, tanto de hardware quanto de software.

Com as características do projeto em mente, foi escolhido o modelo **COCOMO Intermediário Semidestacado**, que, por sua vez, apresenta um conjunto de atributos direcionadores de custo que se agrupam em 4 categorias: atributos do produto, atributos do hardware, atributos de pessoal e atributos de projeto. Para o projeto Fluxo Ágil, foi decidido que a estimativa terá enfoque nos seguintes atributos:

- **Atributos do produto:**
  - confiabilidade exigida do software;
  - tamanho do banco de dados;
  - complexidade do produto;
- **Atributos do hardware:**
  - restrições ao tempo de execução;
- **Atributos de pessoal:**
  - experiência em aplicações;
  - capacidade do programador;
- **Atributos de projeto:**
  - uso de práticas modernas de programação;
  - uso de ferramentas de software;
  - cronograma exigido de desenvolvimento;

Esses atributos são então classificados em uma escala que varia de "muito baixo" a "extremamente elevado", e a partir disso se determina o multiplicador de esforço de cada atributo. A tabela a seguir traz os multiplicadores de esforço dos atributos escolhidos (de acordo com Boehm, 1981), onde os números **destacados** são as classificações escolhidas para esse projeto.

| Direcionadores de Custo                 | Muito Baixo | Baixo    | Normal   | Elevado  | Muito Elevado | Extremamente Elevado |
| --------------------------------------- | ----------- | -------- | -------- | -------- | ------------- | -------------------- |
| Confiabilidade exigida do software      | 0.75        | 0.88     | **1.00** | 1.15     | 1.40          | -                    |
| Tamanho do banco de dados               | -           | **0.94** | 1.00     | 1.08     | 1.16          | -                    |
| Complexidade do produto                 | 0.70        | **0.85** | 1.00     | 1.15     | 1.30          | 1.65                 |
| Restrições ao tempo de execução         | -           | -        | **1.00** | 1.11     | 1.30          | 1.66                 |
| Experiência em aplicações               | 1.29        | **1.13** | 1.00     | 0.91     | 0.82          | -                    |
| Capacidade do programador               | 1.42        | **1.17** | 1.00     | 0.86     | 0.70          | -                    |
| Uso de práticas modernas de programação | 1.24        | 1.10     | 1.00     | **0.91** | 0.82          | -                    |
| Uso de ferramentas de software          | 1.24        | 1.10     | 1.00     | **0.91** | 0.83          | -                    |
| Cronograma exigido de desenvolvimento   | 1.23        | 1.08     | 1.00     | **1.04** | 1.10          | -                    |
<p align = "center"> 
Tabela 1 - Multiplicadores de esforço <br>
Fonte: Boehm (1981) 
</p>

Além disso, na estimativa também são usados coeficientes pre-determinados, representados na tabela a seguir, onde os coeficientes **a** e **b** são do COCOMO Intermediário, e **c** e **d** são reutilizados do COCOMO Básico. 

| Projeto de Software | a    | b    | c    | d    |
| ------------------- | ---- | ---- | ---- | ---- |
| Orgânico            | 3.20 | 1.05 | 2.50 | 0.38 |
| Semidestacado       | 3.00 | 1.12 | 2.50 | 0.35 |
| Embutido            | 2.80 | 1.20 | 2.50 | 0.32 |
<p align = "center"> 
Tabela 2 - Coeficientes <br>
Fonte: Boehm (1981) 
</p>

Portanto, como o projeto utilizará o COCOMO Intermediário Semidestacado, temos que: a = 3.00, b = 1.12, c = 2.50 e d = 0.35 .

## Resultados

### Cálculo da estimativa de esforço

No modelo COCOMO Intermediário, usa-se a seguinte equação para a estimativa de esforço:

E = a x S^b x fae,

onde:

- **E**: esforço aplicado, em pessoas-mês.
- **S**: é o número estimado de linhas de código para o projeto (em milhares).
- **a** e **b**: são coeficientes fornecidos na Tabela 2.
- **fae**: é o Fator de Ajustamento do Esforço. É igual ao produto de cada um dos multiplicadores de esforço definidos.

O grupo estimou a seguinte quantidade de linhas:

- Backend:
  - Processamento: 300 linhas
  - Exportar resultado: 300 linhas
- Frontend: 3 páginas, cada uma com 300 linhas (3 x 300 = 900)
- Web Scraper: 300 linhas
- Bancos de Dados: 300 linhas

Ou seja, no total temos que S = 2100loc (lines of code), ou **S = 2.1kloc**.

Calculando fae, temos que:

fae = 1.00 x 0.94 x 0.85 x 1.00 x 1.13 x 1.17 x 0.91 x 0.91 x 1.04

Portanto, **fae ≅ 0.91**

Finalmente, calculando E:

E = 3.00 x (2.1)^(1.12) x 0.91

**E ≅ 6.27 pessoas-mês**

### Cálculo da estimativa de tempo

No modelo COCOMO Intermediário, usa-se a seguinte equação para a estimativa de tempo de desenvolvimento:

T = c x E^d,

onde:

- **E**: é o esforço aplicado, em pessoas-mês.
- **T**: é o tempo de desenvolvimento estimado, em meses cronológicos.
- **c** e **d**: são coeficientes fornecidos na Tabela 2.

Calculando T, então, temos que:

T = 2.50 x (6.27)^(0.35)

**T ≅ 4.75 meses**

## Referências

Meller, Maristela Corrêa. Modelos Para Estimar Custos De Software: Estudo Comparativo Com Softwares De Pequeno Porte. 2002. Disponível em: https://repositorio.ufsc.br/xmlui/handle/123456789/82351. Acesso em: 24/06/22.
