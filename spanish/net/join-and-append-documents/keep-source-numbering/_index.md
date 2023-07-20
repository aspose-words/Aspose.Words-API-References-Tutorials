---
title: Mantener la numeración de fuentes
linktitle: Mantener la numeración de fuentes
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a agregar un documento conservando el formato de numeración de origen en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/keep-source-numbering/
---

Este tutorial explica cómo adjuntar un documento de origen a un documento de destino conservando el formato de numeración original de los párrafos numerados mediante Aspose.Words para .NET.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puedes descargarlo desde[Aspose.Releases]https://releases.aspose.com/words/net/ o use el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se guardarán los documentos de origen y de destino.

## Paso 2: Crear los documentos de origen y de destino

 Crear instancias de`Document` para los documentos de origen y de destino.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: Mantener la numeración de fuentes al importar

 Para conservar el formato de numeración de los párrafos numerados del documento de origen, cree una instancia de`ImportFormatOptions` y establecer`KeepSourceNumbering` a`true` . Usar una`NodeImporter` para importar nodos del documento de origen al documento de destino, especificando`ImportFormatMode.KeepSourceFormatting` y el`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Paso 4: importar y agregar párrafos

 Iterar a través de los párrafos en el documento de origen e importar cada párrafo en el documento de destino utilizando el`importer`. Agregue los nodos importados al cuerpo del documento de destino.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Paso 5: Guarde el documento modificado

 Guarde el documento modificado usando el`Save` metodo de la`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Esto completa la implementación de agregar un documento de origen a un documento de destino mientras se mantiene el formato de numeración original usando Aspose.Words para .NET.

### Ejemplo de código fuente para Keep Source Numbering usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Mantenga el formato de la lista de fuentes al importar párrafos numerados.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```