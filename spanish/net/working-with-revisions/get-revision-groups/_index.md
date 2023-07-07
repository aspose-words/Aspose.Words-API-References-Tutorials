---
title: Obtener grupos de revisión
linktitle: Obtener grupos de revisión
second_title: Referencia de API de Aspose.Words para .NET
description: Obtenga grupos de revisión en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/get-revision-groups/
---

En esta guía paso a paso, le diremos cómo obtener los grupos de revisión en un documento de Word usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

## Paso 1: Cargar el documento

El primer paso es cargar el documento que contiene las revisiones.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Paso 2: Explorar grupos de revisión

A continuación, recorreremos los grupos de revisión presentes en el documento y mostraremos sus detalles, como el autor, el tipo de revisión y el texto revisado.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Ejemplo de código fuente para Obtener grupos de revisión usando Aspose.Words para .NET

Aquí está el código fuente completo para obtener los grupos de revisión en un documento usando Aspose.Words para .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Conclusión

En este tutorial, aprendimos cómo obtener los grupos de revisión en un documento de Word usando Aspose.Words para .NET. Seguimos los pasos para cargar el documento y navegar por los grupos de revisión, mostrando detalles como el autor y el tipo de revisión. Ahora puede aplicar este conocimiento para analizar las revisiones de su propio documento de Word utilizando Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cómo cargar un documento en Aspose.Words para .NET?

 R: Usa el`Document` clase de Aspose.Words para .NET para cargar un documento desde un archivo. Puede especificar la ruta completa del documento.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### P: ¿Cómo buscar grupos de revisión en un documento en Aspose.Words para .NET?

 R: Usa el`Groups` propiedad del documento`Revisions` object para obtener la colección de grupos de revisión. Luego puede usar un ciclo para recorrer cada grupo de revisión.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Procese cada grupo de revisión aquí
}
```

#### P: ¿Cómo obtener el autor de un grupo de revisión en Aspose.Words para .NET?

 R: Usa el`Author` propiedad de la`RevisionGroup` object para obtener el autor del grupo de revisión.

```csharp
string author = group.Author;
```

#### P: ¿Cómo obtener el tipo de revisión de un grupo de revisión en Aspose.Words para .NET?

 R: Usa el`RevisionType` propiedad de la`RevisionGroup`object para obtener el tipo de revisión del grupo.

```csharp
string revisionType = group.RevisionType;
```