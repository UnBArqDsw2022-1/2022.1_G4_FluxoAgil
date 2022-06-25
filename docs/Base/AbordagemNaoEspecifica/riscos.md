# Plano de Riscos

## Histórico de versões
| Data       | Versão | Descrição            | Autor(a)                                     | Revisor(a)                                    |
| ---------- | ------ | -------------------- | -------------------------------------------- | --------------------------------------------- |
| 18.06.2022   | 1.0 | Criação do documento | [Lucas Braun](https://github.com/lbvx) | [Yudi Yamane](https://github.com/yudi-azvd) |

## Introdução

Qualquer processo de desenvolvimento de software envolve riscos, desde problemas na organização até erros técnicos. Este documento, portanto, descreve o plano de riscos utilizado no projeto, identificando e caracterizando riscos que podem ocorrer durante o ciclo do desenvolvimento do software, e propondo soluções para prevení-los e contê-los.

## Metodologia

Para caracterizar cada risco, foram usados 5 componentes:

- **Evento:** Descrição do que pode acontecer.
- **Probabilidade:** A frequência com que pode ocorrer.
- **Impacto:** O quão grave é o seu efeito, caso realmente ocorra.
- **Prevenção:** Como reduzir sua probabilidade.
- **Contenção:** Como reduzir seu impacto, caso realmente ocorra.

As escalas utilizadas para os componentes **impacto** e **probabilidade** são descritas a seguir:

### Probabilidade

| Probabilidade | Descrição |
| --------- | ----- |
| Baixa | Frequência/chance baixa de ocorrer |
| Média | Frequência/chance média de ocorrer |
| Alta | Frequência/chance alta de ocorrer |

### Impacto

| Impacto | Descrição |
| --------- | ----- |
| Baixo | Pouco impacto no projeto |
| Médio | Efeito grave sobre o projeto, mas fácil de recuperar |
| Alto | Impede o prosseguimento do projeto até que seja resolvido |

## Participantes

- [Lucas Braun](https://github.com/lbvx)
- [Matheus Monteiro](https://github.com/matheusyanmonteiro)

## Matriz de Riscos 

| # | Evento | Probabilidade | Impacto | Prevenção | Contenção |
| - | ------ | ------------- | ------- | --------- | --------- |
| 1 | Falta de comprometimento com o projeto | Média | Alto | Ações para manter o engajamento; Comunicação frequente e efetiva | Comunicar com o membro |
| 2 | Distribuição de tarefas desbalanceada | Baixa | Médio | Participação nas sprints; Distribuir balanceadamente considerando a dificuldade das tarefas | Realocação das tarefas |
| 3 | Desistência de um integrante | Baixa | Alto | Manter a motivação através de comunicação frequente | Realocação das tarefas |
| 4 | Alteração no escopo do projeto | Média | Médio | Elicitação e análise de requisitos efetiva desde o início do projeto;  | Documentar bem os novos itens |
| 5 | Má interpretação dos requisitos | Baixa | Alto | Requisitos bem definidos na documentação; Realizar verificação dos requisitos | Aprimorar documentação dos requisitos |
| 6 | Atraso nas entregas | Média | Alta | Comunicação frequente, especialmente durante as sprints | Realocar tarefas atrasadas |
| 7 | Requisitos mal elicitados | Baixa | Alta | Realizar validação de requisitos efetivamente | Comunicar o grupo; Levantar requisitos |
| 8 | Defeitos na aplicação do projeto | Alta | Média | Realizar testes do código; Realizar revisões sobre alterações  | Alocar membros para o conserto do defeito |

## Referências

TOBIAS SCHROEDER; Guia prático para elaborar um plano de riscos completo em 12 etapas. Disponível em: https://blog.softexpert.com/plano-de-riscos-completo-12-etapas/. Acesso em: 18/06/2022