---
title: Comportamiento de estilo inteligente
linktitle: Comportamiento de estilo inteligente
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a mantener un comportamiento de estilo inteligente al unir y adjuntar documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/join-and-append-documents/smart-style-behavior/
---

Este tutorial lo guiará a través del proceso de uso de la función Smart Style Behavior de Aspose.Words para .NET. Esta característica le permite unir y agregar documentos de Word mientras mantiene un comportamiento de estilo inteligente.

## requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1. Aspose.Words para .NET instalado. Puede descargarlo del sitio web de Aspose o instalarlo a través de NuGet.
2. Visual Studio o cualquier otro entorno de desarrollo C#.

## Paso 1: inicialice los directorios de documentos

 Primero, debe establecer la ruta a su directorio de documentos. Modificar el valor de la`dataDir` variable a la ruta donde se encuentran sus documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue los documentos de origen y destino

 A continuación, debe cargar los documentos de origen y destino utilizando Aspose.Words`Document` clase. Actualice los nombres de los archivos en el`Document` constructor de acuerdo con los nombres de sus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Paso 3: inserte un salto de página en el documento de destino

 Para asegurarse de que el contenido adjunto aparece en una nueva página en el documento de destino, puede insertar un salto de página usando un`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Paso 4: Establecer opciones de comportamiento de estilo inteligente

Para habilitar el comportamiento de estilo inteligente durante la operación de agregar, debe crear una instancia de`ImportFormatOptions` y establecer el`SmartStyleBehavior` propiedad a`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Paso 5: agregue el documento de origen al documento de destino

 Ahora, puede agregar el documento de origen al documento de destino usando el`InsertDocument` metodo de la`DocumentBuilder` clase. Utilizar el`ImportFormatMode.UseDestinationStyles` parámetro y pasar el`ImportFormatOptions` objeto para mantener un comportamiento de estilo inteligente.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Paso 6: Guarde el documento final

 Finalmente, guarde el documento fusionado con la función Smart Style Behavior habilitada usando el`Save` metodo de la`Document` clase.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Ejemplo de código fuente para Smart Style Behavior usando Aspose.Words para .NET

Aquí está el código fuente completo para la función "Comportamiento de estilo inteligente" en C# usando Aspose.Words para .NET:
 
```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

¡Eso es todo! Ha implementado con éxito la función Comportamiento de estilo inteligente utilizando Aspose.Words para .NET. El documento final contendrá el contenido combinado con el comportamiento de estilo inteligente mantenido.