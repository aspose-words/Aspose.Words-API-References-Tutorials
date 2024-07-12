---
title: Código embutido
linktitle: Código embutido
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como codificar em linha com o guia passo a passo do Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/inline-code/
---

Neste exemplo, orientaremos você sobre como usar o recurso de código embutido com Aspose.Words for .NET. Código Inline é usado para representar visualmente pedaços de código dentro de um parágrafo.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: adicionar estilo ao código embutido

 Adicionaremos um estilo personalizado para o código embutido usando o`Styles.Add` método do`Document` objeto. Neste exemplo, estamos criando um estilo chamado "InlineCode" para código embutido com um crase padrão.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Etapa 3: adicionar código embutido

Agora podemos adicionar código embutido usando o estilo personalizado "InlineCode". Neste exemplo, adicionamos dois trechos de texto com números diferentes de crases.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Exemplo de código-fonte para código embutido com Aspose.Words para .NET

```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

// O número de crases foi perdido, um crase será usado por padrão.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Serão 3 crases.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Parabéns! Agora você aprendeu como usar a funcionalidade de código embutido com Aspose.Words for .NET.


### Perguntas frequentes

#### P: Como posso usar o código embutido no Aspose.Words?

 R: Para usar código embutido no Aspose.Words, você pode usar tags apropriadas para circundar o texto a ser formatado como código embutido. Por exemplo, você pode usar o`<code>` ou`<kbd>` tag para cercar o texto a ser formatado como código embutido.

#### P: É possível especificar a fonte ou cor do código embutido no Aspose.Words?

 R: Sim, você pode especificar a fonte ou cor do código embutido em Aspose.Words. Você pode usar o`Font.Name`e`Font.Color` propriedades do`Run` objeto para definir a fonte e a cor do código embutido. Por exemplo, você pode usar`run.Font.Name = "Courier New"` para especificar a fonte do código embutido e`run.Font.Color = Color.Blue`para especificar a cor.

#### P: Posso usar o código embutido em um parágrafo que contém outros elementos de texto?

 R: Sim, você pode usar o código embutido em um parágrafo que contenha outros elementos de texto. Você pode criar vários`Run` objetos para representar diferentes partes do parágrafo e, em seguida, use tags de código embutido para formatar apenas as partes específicas como código embutido. Então você pode adicioná-los ao parágrafo usando o`Paragraph.AppendChild(run)` método.