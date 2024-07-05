---
title: Texto em itálico
linktitle: Texto em itálico
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como colocar texto em itálico com o guia passo a passo do Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/italic-text/
---

Neste exemplo, orientaremos você sobre como usar o recurso de texto em itálico com Aspose.Words for .NET. O texto em itálico é usado para enfatizar certas partes de um documento.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: colocar o texto em itálico

 Podemos colocar o texto em itálico definindo a fonte`Italic`propriedade para`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Exemplo de código-fonte para texto em itálico com Aspose.Words for .NET


```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

// Deixe o texto em itálico.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

Parabéns! Agora você aprendeu como usar o recurso de texto em itálico com Aspose.Words for .NET.


### Perguntas frequentes

#### P: Como posso colocar o texto em itálico no Aspose.Words?

R: Para colocar o texto em itálico no Aspose.Words, você pode usar o`Font.Italic` propriedade do`Run`objeto. Você pode definir esta propriedade como`true` para colocar em itálico um texto específico. Por exemplo, você pode usar`run.Font.Italic=true` colocar em itálico o texto contido no`Run` objeto.

#### P: É possível colocar vários trechos de texto em itálico no mesmo parágrafo?

 R: Sim, você pode colocar em itálico vários trechos de texto em um único parágrafo usando vários`Run` objetos. Você pode criar vários`Run` objetos e definir o`Font.Italic`propriedade para`true` para cada objeto colocar em itálico as partes desejadas do texto. Então você pode adicioná-los ao parágrafo usando o`Paragraph.AppendChild(run)` método.

#### P: Posso colocar em itálico o texto que está em uma tabela ou célula no Aspose.Words?

 R: Sim, você pode colocar em itálico o texto que está em uma tabela ou célula no Aspose.Words. Você pode navegar até a célula ou parágrafo desejado usando os métodos apropriados e, em seguida, aplicar a formatação em itálico usando o`Font.Italic` propriedade do`Run` ou`Paragraph` objeto.