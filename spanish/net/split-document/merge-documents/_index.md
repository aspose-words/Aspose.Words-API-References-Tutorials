---
title: Fusionar documentos
linktitle: Fusionar documentos
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para explicar el código fuente C# de la función Merge Documents de Aspose.Words para .NET
type: docs
weight: 10
url: /es/net/split-document/merge-documents/
---

En este tutorial, lo guiaremos a través de cómo fusionar varios documentos de Word utilizando la función Fusionar documentos de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y obtener un documento combinado que contenga todos los documentos fuente.

## Paso 1: busque documentos para fusionar

Antes de fusionar los documentos, debemos ubicar los documentos de origen que se fusionarán. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Busque documentos para fusionar.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Paso 2: Combinar documentos

Ahora fusionaremos los documentos uno por uno para crear un documento fusionado final. Así es cómo:

```csharp
// Abra la primera parte del documento resultante.
Document sourceDoc = new Document(sourceDocumentPath);

// Cree un nuevo documento resultante.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Combinar los documentos uno por uno.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Ejemplo de código fuente para fusionar documentos usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Fusionar documentos de Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Encuentre documentos usando para fusionar.
	FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
		.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
	string sourceDocumentPath =
		Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

	// Abra la primera parte del documento resultante.
	Document sourceDoc = new Document(sourceDocumentPath);

	// Cree un nuevo documento resultante.
	Document mergedDoc = new Document();
	DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

	// Combine las partes del documento una por una.
	foreach (FileSystemInfo documentPath in documentPaths)
	{
		if (documentPath.FullName == sourceDocumentPath)
			continue;

		mergedDocBuilder.MoveToDocumentEnd();
		mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
		sourceDoc = new Document(documentPath.FullName);
	}

	mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");

```
