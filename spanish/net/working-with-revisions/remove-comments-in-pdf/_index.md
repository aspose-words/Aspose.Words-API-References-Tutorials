---
title: Eliminar comentarios en PDF
linktitle: Eliminar comentarios en PDF
second_title: Referencia de API de Aspose.Words para .NET
description: Elimine comentarios en un archivo PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/remove-comments-in-pdf/
---

En esta guía paso a paso, le diremos cómo eliminar comentarios en un archivo PDF usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

## Paso 1: Cargar el documento

El primer paso es cargar el documento que contiene los comentarios.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Paso 2: ocultar comentarios en PDF

Configuraremos la opción de diseño para ocultar comentarios al generar el PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Paso 3: Guarde el documento como PDF

Finalmente, guardaremos el documento en formato PDF borrando los comentarios.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Formatos de salida de rebajas

La salida se puede formatear en Markdown para mejorar la legibilidad. Por ejemplo :

```markdown
- Comments are hidden in the generated PDF.
```

### Ejemplo de código fuente para Eliminar comentarios en PDF usando Aspose.Words para .NET

Aquí está el código fuente completo para eliminar comentarios en un archivo PDF usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Revisions.docx");

	// Ocultar comentarios en el PDF.
	doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

	doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");

```