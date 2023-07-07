---
title: Eliminar comentarios en archivo PDF
linktitle: Eliminar comentarios en archivo PDF
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

## Conclusión

En este tutorial, aprendimos cómo eliminar comentarios de un archivo PDF usando Aspose.Words para .NET. Al usar las opciones de diseño adecuadas, pudimos ocultar los comentarios al generar el PDF. Aspose.Words for .NET ofrece una gran flexibilidad para manipular archivos de Word y convertirlos a diferentes formatos, incluido PDF. Ahora puede aplicar este conocimiento para eliminar comentarios en sus propios archivos PDF utilizando Aspose.Words para .NET.

### Preguntas frecuentes para eliminar comentarios en un archivo pdf

#### P: ¿Cómo cargar un documento en Aspose.Words para .NET?

 R: Usa el`Document` clase de Aspose.Words para .NET para cargar un documento desde un archivo. Puede especificar la ruta completa del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: ¿Cómo ocultar comentarios en PDF generados con Aspose.Words para .NET?

 R: Usa el`CommentDisplayMode` propiedad de la`LayoutOptions` objeto para configurar cómo se muestran los comentarios al generar el PDF. Para ocultar comentarios, establezca esta propiedad en`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### P: ¿Cómo guardar un documento como PDF con Aspose.Words para .NET?

 R: Usa el`Save` metodo de la`Document` objeto para guardar el documento en formato PDF. Especifique la ruta completa del archivo PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```