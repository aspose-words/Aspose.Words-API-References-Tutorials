---
title: Por Secciones
linktitle: Por Secciones
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a dividir un documento de Word en secciones separadas usando Aspose.Words para .NET con un ejemplo de código completo.
type: docs
weight: 10
url: /es/net/split-document/by-sections/
---

En este ejemplo, le mostraremos cómo dividir un documento de Word en secciones separadas mediante la función Por secciones de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y obtener documentos separados para cada sección.

## Paso 1: Cargar el documento

Para comenzar, necesitamos especificar el directorio de su documento y cargar el documento en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Paso 2: Divide el documento en secciones

Ahora vamos a iterar a través de cada sección del documento y dividir el documento en partes más pequeñas, sección por sección. Aquí está cómo hacerlo:

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// Divide el documento en partes más pequeñas, en este caso, separándolo por secciones.
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// Guarde cada sección como un documento separado.
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### Código fuente de ejemplo para Por secciones usando Aspose.Words para .NET

Aquí está el código fuente completo de la función Por secciones de Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	for (int i = 0; i < doc.Sections.Count; i++)
	{
		// Dividir un documento en partes más pequeñas, en este caso, dividir por sección.
		Section section = doc.Sections[i].Clone();

		Document newDoc = new Document();
		newDoc.Sections.Clear();

		Section newSection = (Section) newDoc.ImportNode(section, true);
		newDoc.Sections.Add(newSection);

		// Guarde cada sección como un documento separado.
		newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
	}

```

Con este código podrá dividir un documento de Word en secciones separadas utilizando Aspose.Words para .NET.

Ahora puedes trabajar fácilmente con secciones específicas.

