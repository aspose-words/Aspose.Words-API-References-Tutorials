---
title: Texto em negrito
linktitle: Texto em negrito
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como colocar texto em negrito com o guia passo a passo do Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/bold-text/
---

Neste exemplo, vamos dizer como colocar texto em negrito com Aspose.Words for .NET. O texto em negrito torna-o mais visível e dá mais destaque.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: texto em negrito

 Podemos colocar o texto em negrito definindo o construtor de documentos`Font.Bold`propriedade para`true`.

```csharp
builder.Font.Bold = true;
```

## Etapa 3: adicione conteúdo ao documento

 Agora podemos adicionar conteúdo ao documento usando os métodos do construtor de documentos, como`Writeln`, que adiciona uma linha de texto.

```csharp
builder.Writeln("This text will be bold");
```

## Exemplo de código-fonte para texto em negrito usando Aspose.Words para .NET


```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

// Deixe o texto em negrito.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Parabéns! Agora você aprendeu como colocar texto em negrito com Aspose.Words for .NET.


### Perguntas frequentes

#### P: Como posso deixar o texto em negrito no Aspose.Words?

 R: Para deixar o texto em negrito no Aspose.Words, você pode usar o`Font.Bold` propriedade do`Run` objeto. Você pode definir esta propriedade como`true` para texto específico em negrito. Por exemplo, você pode usar`run.Font.Bold=true` colocar em negrito o texto dentro do`Run` objeto.

#### P: É possível colocar em negrito vários trechos de texto no mesmo parágrafo?

 R: Sim, você pode colocar em negrito vários trechos de texto em um único parágrafo usando vários`Run` objetos. Você pode criar vários`Run` objetos e definir o`Font.Bold`propriedade para`true` para cada objeto coloque em negrito as partes desejadas do texto. Então você pode adicioná-los ao parágrafo usando o`Paragraph.AppendChild(run)` método.

#### P: Posso colocar texto em negrito em uma tabela ou célula no Aspose.Words?

 R: Sim, você pode colocar texto em negrito em uma tabela ou célula no Aspose.Words. Você pode navegar até a célula ou parágrafo desejado usando os métodos apropriados e, em seguida, aplicar a formatação em negrito usando o`Font.Bold` propriedade do`Run` ou`Paragraph` objeto.