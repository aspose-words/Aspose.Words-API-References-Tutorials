---
title: Usar estilos de destino
linktitle: Usar estilos de destino
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a unir y anexar documentos de Word mientras aplica estilos de documento de destino utilizando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/use-destination-styles/
---

Este tutorial lo guiará a través del proceso de uso de la función Usar estilos de destino de Aspose.Words para .NET. Esta función le permite unir y adjuntar documentos de Word mientras aplica los estilos del documento de destino.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Aspose.Words para .NET instalado. Puede descargarlo del sitio web de Aspose o instalarlo a través de NuGet.
2. Visual Studio o cualquier otro entorno de desarrollo C#.

## Paso 1: inicializar los directorios de documentos

 Primero, debe establecer la ruta a su directorio de documentos. Modificar el valor de la`dataDir` variable a la ruta donde se encuentran sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue los documentos de origen y de destino

 A continuación, debe cargar los documentos de origen y de destino utilizando Aspose.Words.`Document` clase. Actualice los nombres de los archivos en el`Document` constructor de acuerdo con los nombres de sus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: agregue el documento de origen con estilos de destino

 Para adjuntar el documento de origen al documento de destino mientras se aplican los estilos del documento de destino, puede utilizar el`AppendDocument` método de la`Document` clase con el`ImportFormatMode.UseDestinationStyles` parámetro.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Paso 4: guarde el documento final

 Finalmente, guarde el documento combinado con la función Usar estilos de destino habilitada usando el`Save` método de la`Document` clase.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Código fuente de ejemplo para usar estilos de destino usando Aspose.Words para .NET

Aquí está el código fuente completo para la función "Usar estilos de destino" en C# usando Aspose.Words para .NET:

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Adjunte el documento de origen utilizando los estilos del documento de destino.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

¡Eso es todo! Ha implementado con éxito la función Usar estilos de destino utilizando Aspose.Words para .NET. El documento final contendrá el contenido combinado con los estilos del documento de destino aplicados.