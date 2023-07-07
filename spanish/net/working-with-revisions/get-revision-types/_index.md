---
title: Obtener tipos de palabras de revisión
linktitle: Obtener tipos de palabras de revisión
second_title: Referencia de API de Aspose.Words para .NET
description: Obtenga tipos de revisión de palabras en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/get-revision-types/
---

En esta guía paso a paso, le diremos cómo obtener las revisiones de tipos de palabras en un documento de Word usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

## Paso 1: Cargar el documento

El primer paso es cargar el documento que contiene las revisiones.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Paso 2: recorre los párrafos

A continuación, repasaremos los párrafos del documento y comprobaremos los tipos de revisiones de palabras asociadas con cada párrafo.

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

### Código fuente de ejemplo para Obtener tipos de revisión usando Aspose.Words para .NET

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

En este tutorial, aprendimos cómo obtener los tipos de revisiones de palabras en un documento de Word usando Aspose.Words para .NET. Seguimos los pasos para cargar el documento, revisar los párrafos y verificar los tipos de reseñas de palabras asociadas con cada párrafo. Ahora puede aplicar este conocimiento para analizar reseñas de palabras en sus propios documentos de Word utilizando Aspose.Words para .NET.

### Preguntas frecuentes para obtener tipos de revisión de palabras

#### P: ¿Cómo cargar un documento en Aspose.Words para .NET?

 R: Usa el`Document` clase de Aspose.Words para .NET para cargar un documento desde un archivo. Puede especificar la ruta completa del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: ¿Cómo recorro los párrafos de un documento en Aspose.Words para .NET?

 R: Usa el`Paragraphs` propiedad de la sección del documento para obtener la colección de párrafos. A continuación, puede utilizar un bucle para recorrer cada párrafo.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Procese cada párrafo aquí
}
```

#### P: ¿Cómo verificar si un párrafo se ha movido (eliminado) en Aspose.Words para .NET?

 R: Use un párrafo`IsMoveFromRevision` propiedad para comprobar si se ha movido (eliminado).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // El párrafo ha sido movido (eliminado)
}
```

#### P: ¿Cómo verificar si un párrafo se ha movido (insertado) en Aspose.Words para .NET?

 R: Use un párrafo`IsMoveToRevision`propiedad para comprobar si se ha movido (insertado).

```csharp
if (paragraph.IsMoveToRevision)
{
     // El párrafo ha sido movido (insertado)
}
```