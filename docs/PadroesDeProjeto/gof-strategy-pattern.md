# GoF: Strategy Pattern

## Histórico de versões
| Data       | Versão | Descrição            | Autor(a)                                    | Revisor(a)                                    |
| ---------- | ------ | -------------------- | ------------------------------------------- | --------------------------------------------- |
| 01/08/2022 | 1.0    | Criação do documento | [Yudi Yamane](https://github.com/yudi-azvd) | [Thaís Rebouças](https://github.com/Thais-ra) |

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

```ts
interface Exporter {
    async export(courses: Courses[][]);
}

// text-exporter.ts
class TextExporter implements Exporter {
    async export(courses: Courses[][]) {
        let resultText = '# Fluxo de Disciplinas\n\n'
        courses.forEach((coursesInPeriod, semesterIndex) => {
            resultText += `## Período ${semesterIndex}\n\n`
            let coursesInPeriodAsString = coursesInPeriod
                .reduce((accumulator, current) => accumulator + `- ${current}\n`, '')
            resultText += coursesInPeriodAsString
        })

        File.save('Fluxo de matérias.md', resultText)
    }

    // Outra opção
    // https://code.tutsplus.com/tutorials/how-to-save-a-file-with-javascript--cms-41105
    saveFile(resultText: string) {
        // https://stackoverflow.com/questions/13405129/create-and-save-a-file-with-javascript
        const file = new Blob([resultText])
        const file = new Blob([data], {type: type});
        if (window.navigator.msSaveOrOpenBlob) // IE10+
            window.navigator.msSaveOrOpenBlob(file, filename);
        else { // Others
            const a = document.createElement("a");
            const url = URL.createObjectURL(file);
            a.href = url;
            a.download = filename;
            document.body.appendChild(a);
            a.click();
            setTimeout(function() {
                document.body.removeChild(a);
                window.URL.revokeObjectURL(url);  
            }, 0); 
        }
    }
}

// pdf-exporter.ts
import ReactPDF from '@react-pdf/renderer'
import { Page, Text, View, Document, StyleSheet } from '@react-pdf/renderer'

const styles = { /* ... */ }

class PdfExporter implements Exporter {
    async export(courses: Courses[][]) {
        let resultText = '# Fluxo de Disciplinas\n\n'
        courses.forEach((coursesInPeriod, semesterIndex) => {
            resultText += `## Período ${semesterIndex}\n\n`
            let coursesInPeriodAsString = coursesInPeriod
                .reduce((accumulator, current) => accumulator + `- ${current}\n`, '')
            resultText += coursesInPeriodAsString
        })

        PdfLibrary.save('Fluxo de matérias.md', resultText)
    }
}

// image-exporter.ts
import ImageLibrary from 'image-library'

class ImageExporter implements Exporter {
    async export(courses: Courses[][]) {
        
    }
}

// Fazendo o papel de Context
function onExportButtonClick() {
        
    exporter.export(courses)
}

```


## Referências

DESIGN Patterns: Elements of Reusable Object-Oriented Software. [S. l.: s. n.], 1994.