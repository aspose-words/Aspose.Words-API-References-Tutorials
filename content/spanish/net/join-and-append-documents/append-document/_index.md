---
title: Anexar documento
linktitle: Anexar documento
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo adjuntar el contenido de un documento a otro usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/append-document/
---

Este tutorial explica cómo usar Aspose.Words para .NET para agregar el contenido de un documento a otro. El código fuente proporcionado demuestra cómo abrir los documentos de origen y de destino, importar y agregar secciones del documento de origen al documento de destino.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puedes descargarlo desde[Aspose.Releases]https://releases.aspose.com/words/net/ o utilice el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio de documentos donde se encuentran los documentos de origen y de destino.

## Paso 2: abra los documentos de origen y destino

 Abra los documentos de origen y destino utilizando el`Document` constructor de clases. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: agregue secciones del documento de origen al documento de destino

 Recorra todas las secciones del documento de origen e importe cada sección al documento de destino utilizando el`ImportNode` método. Luego, agregue la sección importada al documento de destino.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Paso 4: guarde el documento de destino

 Finalmente, guarde el documento de destino modificado usando el`Save` método de la`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Esto completa la implementación de agregar un documento usando Aspose.Words para .NET.

### Código fuente de ejemplo para anexar documento usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Recorra todas las secciones del documento fuente.
	// Los nodos de sección son hijos inmediatos del nodo Documento, por lo que podemos simplemente enumerar el Documento.
	foreach (Section srcSection in srcDoc)
	{
		// Debido a que estamos copiando una sección de un documento a otro,
		// es necesario importar el nodo Sección al documento de destino.
		// Esto ajusta cualquier referencia específica del documento a estilos, listas, etc.
		//
		// Importar un nodo crea una copia del nodo original, pero la copia
		// ss listo para ser insertado en el documento de destino.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Ahora el nuevo nodo de sección se puede agregar al documento de destino.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```