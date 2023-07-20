---
title: Unirse Continuo
linktitle: Unirse Continuo
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a unir dos documentos de forma continua conservando el formato con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/join-continuous/
---

Este tutorial explica cómo unir dos documentos continuamente usando Aspose.Words para .NET. El código fuente provisto muestra cómo agregar un documento al final de otro documento manteniendo el formato original.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puedes descargarlo desde[Aspose.Releases]https://releases.aspose.com/words/net/ o use el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se encuentran los documentos de origen y de destino.

## Paso 2: Abra los documentos de origen y destino

 Abra los documentos de origen y de destino con el`Document` constructor de clases. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: Configure el inicio de la sección continua

Para que el documento de origen aparezca justo después del contenido del documento de destino, configure el`SectionStart` propiedad de la primera sección en el documento fuente para`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Paso 4: Adjunte el documento de origen

 Añada el documento de origen al documento de destino utilizando el`AppendDocument` metodo de la`Document` clase. Establezca el modo de formato de importación en`ImportFormatMode.KeepSourceFormatting` para conservar los estilos originales del documento de origen.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 5: Guarde el documento modificado

 Finalmente, guarde el documento de destino modificado usando el`Save` metodo de la`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Esto completa la implementación de unir dos documentos continuamente usando Aspose.Words para .NET.

### Ejemplo de código fuente para Join Continuous usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Haga que el documento aparezca inmediatamente después del contenido de los documentos de destino.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Agregue el documento de origen utilizando los estilos originales que se encuentran en el documento de origen.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```