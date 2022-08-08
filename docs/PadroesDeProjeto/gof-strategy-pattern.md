# GoF: Strategy Pattern

## Histórico de versões
| Data       | Versão | Descrição            | Autor(a)                                                                   | Revisor(a)                               |
| ---------- | ------ | -------------------- | -------------------------------------------------------------------------- | ---------------------------------------- |
| 01/08/2022 | 1.0    | Criação do documento | [Yudi](https://github.com/yudi-azvd), [Thaís](https://github.com/Thais-ra) | [Irwin](https://github.com/irwinschmitt) |

## Introdução

O Strategy Pattern é utilizado para selecionar em tempo de execução uma estratégia
ou algoritmo para executar uma tarefa. Essas estratégias são intercambiáveis e 
devem ter a mesma interface pública para o cliente.

As partes que mais aparecem quando esse padrão é implementado são:

- **Estratégia**: classe abstrata ou interface comum da qual as diferentes 
estratégias concretas devem derivar. Se houver alguma rotina em comum para todas
as rotinas concretas, ela pode ser implementada nessa classe para evitar repetição.
- **Estratégia concreta**: classe concreta que estende ou implementa a classe 
abstrata ou interface de estratégia base. Cada estratégia concreta implementa um
algoritmo diferente.
- **Contexto**: classe que tem a referência para uma estratégia e a executa.

## Metodologia

Pensando em umas das funcionalidades do aplicativo, os participantes pensaram
como poderia ser o código referente à exportação do fluxo. É requisito do sistema
exportar os fluxo gerado para um arquivo PDF, imagem ou texto e o usuário deve
ter a possibilidade de escolher entre essas opções de exportação.

## Participantes

- [Yudi Yamane](https://github.com/yudi-azvd)
- [Thaís Rebouças](https://github.com/Thais-ra)

## Resultados

<p align="center">
    <img src="images/padroes-projeto/gofs-strategy.png"/>
</p>
<p align = "center"> 
Figura 1 - Diagrama ilustrando a ideia do padrão de estratégia.<br>
Fonte: Yudi Yamane
</p>

### Exemplo de código

Seguem as classes que implementam o contexto da Figura 1:

```ts
interface Exporter {
    async export();
}

class ExporterContext {
    exporter: Exporter

    setExporter(exporter: Exporter) {
        this.exporter = exporter
    }

    export() {
        this.exporter.export()
    }
}
```

`text-exporter.ts`

```ts
class TextExporter implements Exporter {
    async export() {
        let resultText = '# Fluxo de Disciplinas\n\n'
        courses.forEach((coursesInPeriod, semesterIndex) => {
            resultText += `## Período ${semesterIndex}\n\n`
            let coursesInPeriodAsString = coursesInPeriod
                .reduce((accumulator, current) => accumulator + `- ${current}\n`, '')
            resultText += coursesInPeriodAsString
        })

        // Função fictícia
        window.saveFile('Fluxo de matérias.md', resultText)
    }
}
```

`pdf-exporter.ts`

```ts
import pdfMake from 'pdfmake/build/pdfmake';

class PdfExporter implements Exporter {
    constructor(
        // é usado em pdfProps que é usado em documentDefinitions
        private readonly htmlElementRef: HTMLElement
    ) {}

    async export() {
        // ... definição de estilos e props do PDF ...
        pdfMake.createPdf(documentDefinitions).download()
    }
}

```

`image-exporter.ts`

```ts
import ImageLibrary from 'image-library'

class ImageExporter implements Exporter {
    constructor(
        private readonly courses: Course[][]
    ) {}

    async export() {
        // código para salvar imagem
    }
}
```

Código cliente React: no componente de exportação

```ts
// o caminho para importação não é importante
import ImageExporter from './ImageExporter'
import TextExporter from './TextExporter'
import PdfExporter from './PdfExporter'

function onImageExportButtonClick() {
    exporterContext.setExporter(new ImageExporter(courses))
    exporterContext.export()
}

function onTextExportButtonClick() {
    exporterContext.setExporter(new TextExporter(courses))
    exporterContext.export()
}

function onPdfExportButtonClick() {
    exporterContext.setExporter(new PdfExporter(fluxogramRef))
    exporterContext.export()
}
```

As funções `on...ExportButtonClick` são conectadas ao botões de exportar pela
propriedade `onClick` dos botões, que foram omitidos por brevidade.

Esse código ainda não foi implementado, por isso não há um link para ele.

## Referências

DESIGN Patterns: Elements of Reusable Object-Oriented Software. [S. l.: s. n.], 1994.