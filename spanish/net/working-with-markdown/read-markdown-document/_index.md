---
title: Leer documento de descuento
linktitle: Leer documento de descuento
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a leer un documento de rebajas con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/read-markdown-document/
---

En este ejemplo, lo guiaremos a través de cómo leer un documento de Markdown usando Aspose. Words for .NET Markdown es un lenguaje de marcado liviano que se usa para formatear texto sin formato.

## Paso 1: Leer el documento de Markdown

 Primero, usaremos el`Document` class para leer el documento Markdown. Necesitamos especificar la ruta del archivo Markdown para leer.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");
```

## Paso 2: Elimina el formato del encabezado

Podemos eliminar el formato del encabezado en el último párrafo del documento. En este ejemplo, asignamos el estilo "Cita" al párrafo.

```csharp
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];
```

## Paso 3: Guardar el documento

Finalmente, podemos guardar el documento en el formato deseado.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

### Ejemplo de código fuente para leer un documento Markdown con Aspose.Words para .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");

// Eliminemos el formato de encabezado de una cita en el último párrafo.
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];

doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

¡Felicidades! Ahora ha aprendido a leer un documento Markdown con Aspose.Words para .NET.

