---
title: Acceder a la versión revisada
linktitle: Acceder a la versión revisada
second_title: Referencia de API de Aspose.Words para .NET
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


