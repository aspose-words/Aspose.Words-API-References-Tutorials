---
title: Acceder a la versión revisada
linktitle: Acceder a la versión revisada
second_title: API de procesamiento de documentos de Aspose.Words
description: Acceda a una versión revisada de un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/access-revised-version/
---

En esta guía paso a paso, le mostraremos cómo acceder a la versión revisada de un documento de Word utilizando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

## Paso 1: Cargar el documento

El primer paso es cargar el documento que contiene las revisiones.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Paso 2: Accede a la versión revisada

Ahora pasaremos a la versión revisada del documento.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Paso 3: buscar revisiones

A continuación, recorreremos las revisiones presentes en el documento y mostraremos información específica para los párrafos que son elementos de la lista.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Ejemplo de código fuente para la versión revisada de Access usando Aspose.Words para .NET

Aquí está el código fuente completo para acceder a la versión revisada de un documento usando Aspose.Words para .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Cambiar a la versión revisada del documento.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## Conclusión

En este tutorial, aprendimos cómo acceder a la versión revisada de un documento de Word utilizando Aspose.Words para .NET. Al cargar el documento, navegar a la versión revisada y examinar las revisiones, pudimos obtener información específica para los párrafos que son elementos de la lista. Aspose.Words para .NET ofrece potentes funciones para manipular documentos de Word, incluido el acceso a reseñas. Ahora puede usar este conocimiento para acceder a la versión revisada de sus propios documentos de Word usando Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cómo cargo un documento con revisiones en Aspose.Words para .NET?

 R: Usa el`Document`clase de Aspose.Words para .NET para cargar un documento desde un archivo que contiene revisiones. Puede especificar la ruta completa del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: ¿Cómo accedo a la versión revisada de un documento en Aspose.Words para .NET?

 R: Usa el`RevisionsView`propiedad de la`Document` oponerse a acceder a la versión revisada del documento. Puede establecer el valor de la`RevisionsView` propiedad a`RevisionsView.Final` para mostrar la versión final sin las revisiones.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### P: ¿Cómo busco revisiones de documentos en Aspose.Words para .NET?

 R: Usa un`foreach` loop para iterar a través de las revisiones presentes en el documento. Puedes usar el`Revisions`propiedad de la`Document` object para obtener una colección de todas las revisiones del documento.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Procese cada revisión aquí
}
```

#### P: ¿Cómo verificar si un párrafo es un elemento de lista en Aspose.Words para .NET?

 R: Usa el`IsListItem`propiedad de la`Paragraph` objeto para comprobar si un párrafo es un elemento de lista. El`IsListItem` devoluciones de propiedad`true` si el párrafo es un elemento de lista, de lo contrario, devuelve`false`.

```csharp
if (paragraph.IsListItem)
{
     // El párrafo es un elemento de lista.
}
else
{
     // El párrafo no es un elemento de lista.
}
```