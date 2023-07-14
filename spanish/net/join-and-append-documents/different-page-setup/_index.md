---
title: Configuración de página diferente
linktitle: Configuración de página diferente
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a agregar un documento con diferentes configuraciones de configuración de página usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/different-page-setup/
---

Este tutorial explica cómo usar Aspose.Words para .NET para agregar un documento con diferentes configuraciones de configuración de página a otro documento. El código fuente proporcionado demuestra cómo configurar diferentes configuraciones de página para los documentos de origen y de destino y garantizar una continuación y numeración adecuadas.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo del sitio web oficial de Aspose o usar el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se encuentran los documentos de origen y de destino.

## Paso 2: Abra los documentos de origen y destino

 Abra los documentos de origen y de destino con el`Document` constructor de clases. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: configure los ajustes de página para el documento de origen

Ajuste la configuración de la página del documento de origen para garantizar una continuación y una numeración adecuadas. En este ejemplo, configuramos el inicio de la sección en`SectionStart.Continuous` y reinicie la numeración de páginas. También nos aseguramos de que el ancho, la altura y la orientación de la página coincidan con la última sección del documento de destino.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Paso 4: modificar el formato de párrafo

 Para mantener el formato adecuado, repita todos los párrafos del documento de origen y establezca el`KeepWithNext` propiedad a`true`. Esto asegura que los párrafos permanezcan juntos durante el proceso de adición.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Paso 5: agregue el documento de origen al documento de destino

 Utilizar el`AppendDocument` del documento de destino para agregar el documento de origen modificado al documento de destino, conservando el formato de origen.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 6: Guarde el documento de destino

 Finalmente, guarde el documento de destino modificado usando el`Save` metodo de la`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Esto completa la implementación de agregar un documento con diferentes configuraciones de configuración de página usando Aspose.Words para .NET.

### Código fuente de ejemplo para configuración de página diferente usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Configure el documento de origen para que continúe inmediatamente después del final del documento de destino.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Reinicie la numeración de páginas al principio del documento de origen.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Para asegurarse de que esto no suceda cuando el documento de origen tiene una configuración de página diferente, asegúrese de que el
	// la configuración es idéntica entre la última sección del documento de destino.
	// Si hay más secciones continuas que siguen en el documento fuente,
	// esto deberá repetirse para esas secciones.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Iterar a través de todas las secciones en el documento de origen.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```