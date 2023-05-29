---
title: Obtener detalles del grupo de revisión
linktitle: Obtener detalles del grupo de revisión
second_title: Referencia de API de Aspose.Words para .NET
description: Obtenga detalles del grupo de revisión en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/get-revision-group-details/
---

En esta guía paso a paso, le mostraremos cómo obtener los detalles de un grupo de revisiones en un documento de Word utilizando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

## Paso 1: Cargar el documento

El primer paso es cargar el documento que contiene las revisiones.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Paso 2: buscar revisiones

A continuación, recorreremos las revisiones presentes en el documento y mostraremos sus detalles, como tipo, autor, fecha y texto revisado.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Código fuente de ejemplo para Obtener detalles del grupo de revisión usando Aspose.Words para .NET

Aquí está el código fuente completo para obtener los detalles de un grupo de revisiones en un documento usando Aspose.Words para .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

