---
title: Obtener tipos de palabras de revisión
linktitle: Obtener tipos de palabras de revisión
second_title: API de procesamiento de documentos Aspose.Words
description: Obtenga tipos de revisión de palabras en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/get-revision-types/
---

En esta guía paso a paso, le diremos cómo obtener los tipos de revisiones de palabras en un documento de Word usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de rebajas.

## Paso 1: cargar el documento

El primer paso es subir el documento que contiene las revisiones.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Paso 2: recorra los párrafos

A continuación, revisaremos los párrafos del documento y comprobaremos los tipos de revisiones de palabras asociadas con cada párrafo.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Código fuente de ejemplo para obtener tipos de revisión usando Aspose.Words para .NET

Aquí está el código fuente completo para obtener tipos de revisión en un documento usando Aspose.Words para .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Conclusión

En este tutorial, aprendimos cómo obtener los tipos de revisiones de palabras en un documento de Word usando Aspose.Words para .NET. Seguimos los pasos para cargar el documento, revisar los párrafos y comprobar los tipos de reseñas de palabras asociadas a cada párrafo. Ahora puede aplicar este conocimiento para analizar reseñas de palabras en sus propios documentos de Word utilizando Aspose.Words para .NET.

### Preguntas frecuentes para obtener tipos de palabras de revisión

#### P: ¿Cómo cargar un documento en Aspose.Words para .NET?

 R: Utilice el`Document` clase de Aspose.Words para .NET para cargar un documento desde un archivo. Puede especificar la ruta completa del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: ¿Cómo puedo recorrer los párrafos de un documento en Aspose.Words para .NET?

 R: Utilice el`Paragraphs` propiedad de la sección del documento para obtener la colección de párrafos. Luego puede utilizar un bucle para recorrer cada párrafo.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Procese cada párrafo aquí
}
```

#### P: ¿Cómo comprobar si un párrafo se ha movido (eliminado) en Aspose.Words para .NET?

 R: Utilice un párrafo`IsMoveFromRevision` propiedad para comprobar si se ha movido (eliminado).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // El párrafo ha sido movido (eliminado)
}
```

#### P: ¿Cómo comprobar si un párrafo se ha movido (insertado) en Aspose.Words para .NET?

 R: Utilice un párrafo`IsMoveToRevision`propiedad para comprobar si ha sido movida (insertada).

```csharp
if (paragraph.IsMoveToRevision)
{
     // El párrafo ha sido movido (insertado)
}
```