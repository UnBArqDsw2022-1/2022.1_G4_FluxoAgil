# GoF: Strategy Pattern

## Histórico de versões
| Data       | Versão | Descrição            | Autor(a)                             | Revisor(a)                                                                     |
| ---------- | ------ | -------------------- | ------------------------------------ | ------------------------------------------------------------------------------ |
| 01/08/2022 | 1.0    | Criação do documento | [Yudi](https://github.com/yudi-azvd) | [Thaís](https://github.com/Thais-ra), [Irwin](https://github.com/irwinschmitt) |

## Introdução

O Strategy Pattern é utilizado para selecionar em tempo de execução uma estratégia
ou algoritmo para executar uma tarefa. Essas estratégias são intercambiáveis e 
devem ter a mesma interface pública para o cliente.

As partes que mais aparecem quando esse padrão é implementado são:

- **Estratégia**: classe abstrata ou interface comum da qual as diferentes 
estratégias concretas devem derivar. Se houver alguma rotina em comum para todas
as rotinas concretas, ela pode ser implementada nessa classe para evitar repetição.
- **Estratégia concreta**: classe concreta que extende ou implementa a classe 
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

## Resultados

<img src="images/padroes-projeto/gofs-strategy.png" align = "center" />
<p align = "center"> 
Figura 1 - Diagrama ilustrando a ideia do padrão de estratégia.<br>
Fonte: Yudi Yamane
</p>

### Exemplo de código

Seguem as classes que implementam o contexto da Figura 1:

```tsx
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

// text-exporter.ts
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

// pdf-exporter.ts
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

// image-exporter.ts
import ImageLibrary from 'image-library'

class ImageExporter implements Exporter {
    constructor(
        // é usado em pdfProps que é usado em documentDefinitions
        private readonly courses: Course[][]
    ) {}

    async export() {
        // código para salvar imagem
    }
}

// Fazendo o papel de Context
function onExportButtonClick(type: 'text' | 'pdf' | 'image') {
    const exporterContext = new ExporterContext()

    switch(type): {
        case 'text': 
            exporterContext.setExporter(new TextExporter(courses))
            break
        case 'pdf': 
            exporterContext.setExporter(new PdfExporter(fluxogramRef))
            break
        case 'image': 
            exporterContext.setExporter(new ImageExporter(courses))
            break
    }
        
    exporterContext.export()
}
```

## Referências

DESIGN Patterns: Elements of Reusable Object-Oriented Software. [S. l.: s. n.], 1994.