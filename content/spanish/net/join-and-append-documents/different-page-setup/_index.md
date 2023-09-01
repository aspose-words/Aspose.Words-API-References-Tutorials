---
title: Configuración de página diferente
linktitle: Configuración de página diferente
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo adjuntar un documento con diferentes configuraciones de configuración de página usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/different-page-setup/
---

Este tutorial explica cómo usar Aspose.Words para .NET para agregar un documento con diferentes configuraciones de configuración de página a otro documento. El código fuente proporcionado demuestra cómo configurar diferentes configuraciones de página para los documentos de origen y de destino y garantizar una continuación y numeración adecuadas.

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

## Paso 3: configurar la configuración de página para el documento fuente

 Ajuste la configuración de configuración de página del documento fuente para garantizar una continuación y numeración adecuadas. En este ejemplo, configuramos el inicio de la sección en`SectionStart.Continuous` y reiniciar la numeración de páginas. También nos aseguramos de que el ancho, alto y orientación de la página coincidan con la última sección del documento de destino.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Paso 4: modificar el formato del párrafo

 Para mantener el formato adecuado, repita todos los párrafos del documento fuente y establezca el`KeepWithNext` propiedad a`true`. Esto garantiza que los párrafos permanezcan juntos durante el proceso de adición.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Paso 5: agregue el documento de origen al documento de destino

 Utilizar el`AppendDocument` Método del documento de destino para adjuntar el documento de origen modificado al documento de destino, conservando el formato de origen.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Paso 6: guarde el documento de destino

 Finalmente, guarde el documento de destino modificado usando el`Save` método de la`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Esto completa la implementación de agregar un documento con diferentes configuraciones de configuración de página usando Aspose.Words para .NET.

### Código fuente de ejemplo para una configuración de página diferente usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Configure el documento de origen para que continúe inmediatamente después del final del documento de destino.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Reinicie la numeración de páginas al inicio del documento fuente.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Para garantizar que esto no suceda cuando el documento de origen tiene diferentes configuraciones de configuración de página, asegúrese de que
	//Los ajustes son idénticos entre la última sección del documento de destino.
	// Si hay más secciones continuas a continuación en el documento fuente,
	// Esto deberá repetirse para esas secciones.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Repita todas las secciones del documento fuente.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```