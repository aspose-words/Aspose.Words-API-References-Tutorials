---
title: Obtener tipos de revisión
linktitle: Obtener tipos de revisión
second_title: Referencia de API de Aspose.Words para .NET
description: Obtenga tipos de revisión en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-revisions/get-revision-types/
---

En esta guía paso a paso, le diremos cómo obtener los tipos de revisiones en un documento de Word usando Aspose.Words para .NET. Le proporcionaremos el código fuente completo y le mostraremos cómo formatear la salida de Markdown.

## Paso 1: Cargar el documento

El primer paso es cargar el documento que contiene las revisiones.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Paso 2: recorre los párrafos

A continuación, repasaremos los párrafos del documento y comprobaremos los tipos de revisiones asociados con cada párrafo.

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
