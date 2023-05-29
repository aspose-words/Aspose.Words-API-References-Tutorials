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

continuación, recorreremos los grupos de revisión presentes en el documento y mostraremos sus detalles, como el autor, el tipo de revisión y el texto revisado.

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


