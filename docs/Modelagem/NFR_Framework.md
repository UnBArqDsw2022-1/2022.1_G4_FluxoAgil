# NFR Framework

## Histórico de versões

| Data     | Versão | Descrição  | Autor | Revisor |
| -------- | ------ | ---------- | ----- | ------- |
| 08/07/22 | 1.0    | Criação do documento | [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite) | - |
| 09/07/22 | 1.1    | Inclusão das imagens | [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite) | - |

##  Introdução 
O NFR Framework é uma abordagem proposta por Chung na universidade de Toronto para representar e analisar Requisitos Não-Funcionais. Seu objetivo é ajudar desenvolvedores na implementação de soluções personalizadas, levando em consideração as características do domínio e do sistema em questão. Tais características incluem requisitos não-funcionais, requisitos funcionais, prioridades e carga de trabalho. 

O framework utiliza as softgoals para representar os requisitos não-funcionais, e também, possui um método de análise qualitativa para decidir os status dos softgoals, dado que outros softgoals relacionados foram ou não satisfeitos.


## Metodologia 
Através desse documento definimos as funcionalidades dos requisitos através das possíveis análises, que serão feitas depois da implementação dos diagramas do NFR Framework. Foi utilizada a ferramenta Miro para serem criados os diagramas nfr. 

## Participantes

- [Ana Carolina](https://github.com/AnaCarolinaRodriguesLeite)

## Requisitos não funcionais

Abaixo estão listados os requisitos não-funcionais levantados pelas das técnicas de elicitação utilizadas no projeto, que serão os mesmos utilizados no NFR Framework.

| ID     | Requisitos Não Funcionais                          | Técnica    |
| ------ | -------------------------------------------------- | ---------  |
| RNF01 | O sistema deve ser responsivo                       | [OB01](https://unbarqdsw2022-1.github.io/2022.1_G4_FluxoAgil/#/Base/AbordagemNaoEspecifica/elicitacao/brainstorming?id=requistios-n%c3%a3o-funcionais), [INT03](https://unbarqdsw2022-1.github.io/2022.1_G4_FluxoAgil/#/Base/AbordagemNaoEspecifica/elicitacao/introspeccao?id=requisitos-n%c3%a3o-funcionais) |
| RNF02 | O sistema deve ter consistência entre recomendações | [OB02](https://unbarqdsw2022-1.github.io/2022.1_G4_FluxoAgil/#/Base/AbordagemNaoEspecifica/elicitacao/brainstorming?id=requistios-n%c3%a3o-funcionais) |
| RNF03 | O sistema deve resolver os problemas de pré requisitos   | [OB03](https://unbarqdsw2022-1.github.io/2022.1_G4_FluxoAgil/#/Base/AbordagemNaoEspecifica/elicitacao/brainstorming?id=requistios-n%c3%a3o-funcionais) |
| RNF04 | O sistema deve ter navegabilidade fácil             | [OB04](https://unbarqdsw2022-1.github.io/2022.1_G4_FluxoAgil/#/Base/AbordagemNaoEspecifica/elicitacao/brainstorming?id=requistios-n%c3%a3o-funcionais) |
| RNF05 | O sistema deverá tratar pdf de histórico inválidos  | [OB05](https://unbarqdsw2022-1.github.io/2022.1_G4_FluxoAgil/#/Base/AbordagemNaoEspecifica/elicitacao/brainstorming?id=requistios-n%c3%a3o-funcionais) |
| RNF06 | O sistema deve informar como funciona e utilizar a aplicação  | [INT01](https://unbarqdsw2022-1.github.io/2022.1_G4_FluxoAgil/#/Base/AbordagemNaoEspecifica/elicitacao/introspeccao?id=requisitos-n%c3%a3o-funcionais) |
| RNF07 | O sistema deve sempre mostrar a mesma recomendação se as mesmas opções e disciplinas forem selecionados | [INT02](https://unbarqdsw2022-1.github.io/2022.1_G4_FluxoAgil/#/Base/AbordagemNaoEspecifica/elicitacao/introspeccao?id=requisitos-n%c3%a3o-funcionais) |
| RNF08 | O sistema deve informar o estado atual da aplicação  | [INT04](https://unbarqdsw2022-1.github.io/2022.1_G4_FluxoAgil/#/Base/AbordagemNaoEspecifica/elicitacao/introspeccao?id=requisitos-n%c3%a3o-funcionais) |

<figcation> Tabela 2: Requisitos não funcionais. </figcation>

## Legenda

<center>

![elementos_do_NFR_Framework](https://user-images.githubusercontent.com/49570180/157316868-0d2e5154-355f-490d-9696-7ac1c898d155.jpeg)

</center>

<center>

  <figcaption>
      <b>Imagem 1: Elementos de definição do NFR Framework.</b>
    <br><small>Fonte: própria</small>
  </figcaption>

</center>


<center>

![elementos_de_relacionamento](https://user-images.githubusercontent.com/49570180/157317602-00134891-0e25-4de3-8e14-d5983c8b7daf.jpeg)


</center>

<center>

  <figcaption>
      <b>Imagem 2: Elementos de relacionamento do NFR Framework.</b>
    <br><small>Fonte: própria</small>
  </figcaption>

</center>

<center>

![legenda2](https://user-images.githubusercontent.com/49570180/157535350-9272cbec-4b63-4b30-836b-5ac868130ee7.jpeg)

</center>

<center>

  <figcaption>
      <b>Imagem 3: Tipos de rótulos.</b>
    <br><small>Fonte: própria</small>
  </figcaption>

</center>


## Diagramas

### Diagrama de confiabilidade
![confiabilidade](https://user-images.githubusercontent.com/49570180/178126637-36092897-adad-4675-9da6-efb6c2367cf2.jpg)
  <figcaption> Imagem 4: Diagrama NFR Framework de confiabilidade </figcaption>


### Diagrama de confiabilidade com propagação
![confiabilidade_propagacao](https://user-images.githubusercontent.com/49570180/178126693-4c5dfd0a-7b1d-48db-921b-170facb2c4c4.jpg)
  <figcaption> Imagem 5: Diagrama NFR Framework de confiabilidade com propagação </figcaption>

### Diagrama de usabilidade
![usabilidade](https://user-images.githubusercontent.com/49570180/178126833-08b2d136-32af-471d-92e4-6cefcb2755fb.jpg)
  <figcaption> Imagem 6: Diagrama NFR Framework de usabilidade</figcaption>

### Diagrama de usabilidade com propagação
![usabilidade_propagacao](https://user-images.githubusercontent.com/49570180/178126932-bf411b3e-eb4b-4b9d-9dce-d1c8cbb60b48.jpg)

  <figcaption> Imagem 7: Diagrama NFR Framework de usabilidade com propagação </figcaption>

## Referências

SILVA, Reinaldo Antônio da. NFR4ES:Um Catálogo de Requisitos Não-Funcionais para Sistemas Embarcados. Recife, 201. Disponível em: https://repositorio.ufpe.br/handle/123456789/34150.  Data de acesso: 08/07/2022.
