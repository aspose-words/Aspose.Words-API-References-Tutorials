---
title: Fusionar documentos de Word
linktitle: Fusionar documentos
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a combinar varios documentos de Word utilizando Aspose.Words para .NET. Esta potente API simplifica el proceso de combinación de documentos, haciéndolo eficiente y sencillo.
type: docs
weight: 10
url: /es/net/split-document/merge-documents/
---

En este tutorial, le explicaremos cómo combinar varios documentos de Word utilizando la función Combinar documentos de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y obtener un documento combinado que contenga todos los documentos fuente.

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

## Paso 2: fusionar documentos

Ahora fusionaremos los documentos uno por uno para crear un documento combinado final. Así es cómo:

```csharp
// Abra la primera parte del documento resultante.
Document sourceDoc = new Document(sourceDocumentPath);

// Cree un nuevo documento resultante.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Fusiona los documentos uno por uno.
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

### Código fuente de ejemplo para fusionar documentos usando Aspose.Words para .NET

Aquí está el código fuente completo de la función Fusionar documentos de Aspose.Words para .NET:

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

// Fusionar partes del documento una por una.
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

## Conclusión

¡Felicidades! Ha aprendido a combinar varios documentos de Word utilizando la función Combinar documentos de Aspose.Words para .NET. Siguiendo el código fuente proporcionado, puede combinar documentos separados en un solo documento combinado conservando el formato de cada documento fuente.

Fusionar documentos puede resultar útil cuando desea consolidar información de múltiples fuentes o crear un documento unificado a partir de partes individuales. Aspose.Words para .NET proporciona una potente API que simplifica el proceso de combinación de documentos, haciéndolo eficiente y sencillo.

No dude en explorar otras funciones que ofrece Aspose.Words para .NET para mejorar sus capacidades de procesamiento de documentos y optimizar su flujo de trabajo.

### Preguntas frecuentes

#### ¿Cómo puedo fusionar documentos con diferentes formatos?

 Al fusionar documentos, Aspose.Words para .NET ofrece la opción de conservar el formato de cada documento fuente. Al utilizar el`ImportFormatMode.KeepSourceFormatting` opción, el documento combinado conservará el formato de los documentos originales. Si desea aplicar un formato coherente en todo el documento combinado, puede modificar el formato utilizando la API Aspose.Words después de fusionar los documentos.

#### ¿Puedo fusionar documentos en diferentes formatos?

Sí, Aspose.Words para .NET admite la combinación de documentos en varios formatos, incluidos DOCX, DOC, RTF y más. Puede cargar documentos de diferentes formatos en la API Aspose.Words y fusionarlos en un solo documento independientemente de sus formatos originales.

#### ¿Puedo fusionar documentos con estructuras complejas, como tablas e imágenes?

¡Absolutamente! Aspose.Words para .NET es capaz de fusionar documentos con estructuras complejas, incluidas tablas, imágenes, encabezados, pies de página y más. La API maneja el proceso de fusión preservando al mismo tiempo la integridad y el diseño del contenido de cada documento.

#### ¿Es posible fusionar documentos con diferentes orientaciones o tamaños de página?

Sí, Aspose.Words para .NET maneja documentos con diferentes orientaciones o tamaños de página durante el proceso de fusión. El documento combinado resultante se adaptará a las diferentes orientaciones y tamaños de página de los documentos originales.