---
title: Unirse a nueva página
linktitle: Unirse a nueva página
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo unir dos documentos en una nueva página conservando el formato usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/join-new-page/
---

Este tutorial explica cómo unir dos documentos en una nueva página usando Aspose.Words para .NET. El código fuente proporcionado demuestra cómo agregar un documento al final de otro documento mientras se inicia el documento agregado en una nueva página.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

-  Aspose.Words para la biblioteca .NET instalada. Puedes descargarlo desde[Aspose.Releases]https://releases.aspose.com/words/net/ o utilice el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se encuentran los documentos de origen y de destino.

## Paso 2: abra los documentos de origen y destino

 Abra los documentos de origen y destino utilizando el`Document` constructor de clases. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: configurar el inicio de la sección de nueva página

 Para iniciar el documento adjunto en una nueva página, configure el`SectionStart` propiedad de la primera sección del documento fuente para`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Paso 4: adjuntar el documento fuente

 Adjunte el documento de origen al documento de destino utilizando el`AppendDocument` método de la`Document` clase. Establezca el modo de formato de importación en`ImportFormatMode.KeepSourceFormatting` para preservar los estilos originales del documento fuente.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 5: guarde el documento modificado

Finalmente, guarde el documento de destino modificado usando el`Save` método de la`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Esto completa la implementación de unir dos documentos en una nueva página usando Aspose.Words para .NET.

### Código fuente de ejemplo para unirse a una nueva página usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Configure el documento adjunto para que comience en una página nueva.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Adjunte el documento fuente utilizando los estilos originales que se encuentran en el documento fuente.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```