---
title: Énfasis
linktitle: Énfasis
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar énfasis (negrita y cursiva) con la guía paso a paso de Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/emphases/
---

En este ejemplo, explicaremos cómo usar énfasis con Aspose.Words para .NET. El énfasis se utiliza para enfatizar ciertas partes del texto, como negrita y cursiva.

## Paso 1: inicialización del documento

 Primero, inicializaremos el documento creando una instancia del`Document` clase.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Paso 2: usar un generador de documentos

A continuación, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: agregue texto con énfasis

Podemos agregar texto con énfasis cambiando las propiedades de fuente del generador de documentos. En este ejemplo, utilizamos negrita y cursiva para enfatizar diferentes partes del texto.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Paso 4: guardar el documento

 Finalmente, podremos guardar el documento en el formato deseado. En este ejemplo, estamos usando el`.md` extensión para un formato Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

¡Enhorabuena! Ahora ha aprendido a utilizar énfasis con Aspose.Words para .NET.

### Código fuente de ejemplo para Emphases usando Aspose.Words para .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### Preguntas frecuentes

#### P: ¿Cómo resalto texto usando Markdown?

R: Para resaltar texto usando Markdown, simplemente rodee el texto con los símbolos apropiados. Usar`*` o`_` para cursiva,`**` o`__` por negrita, y`~~` para tachado.

#### P: ¿Podemos combinar diferentes destacados en un mismo texto?

 R: Sí, es posible combinar diferentes resaltados en un mismo texto. Por ejemplo, puede poner en negrita y cursiva una palabra usando ambos`**`y`*` alrededor del mundo.

#### P: ¿Qué opciones de resaltado están disponibles en Markdown?

R: Las opciones de resaltado disponibles en Markdown están en cursiva (`*` o`_`), atrevido (`**` o`__`) y tachado (`~~`).

#### P: ¿Cómo manejo los casos en los que el texto contiene caracteres especiales utilizados por Markdown para resaltar?

 R: Si su texto contiene caracteres especiales utilizados por Markdown para resaltar, puede escapar de ellos precediéndolos con un`\` . Por ejemplo,`\*` mostrará un asterisco literal.

#### P: ¿Podemos personalizar la apariencia del resaltado usando CSS?

R: El resaltado en Markdown generalmente se representa usando los estilos predeterminados del navegador. Si convierte su Markdown a HTML, puede personalizar la apariencia del resaltado usando reglas CSS.