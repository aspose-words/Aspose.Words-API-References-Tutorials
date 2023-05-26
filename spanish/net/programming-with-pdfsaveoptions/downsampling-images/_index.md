---
title: Reducción de resolución de imágenes
linktitle: Reducción de resolución de imágenes
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a reducir la resolución de la imagen al convertir a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/downsampling-images/
---

En este tutorial, lo guiaremos a través de los pasos para reducir la resolución de la imagen al convertir a PDF con Aspose.Words para .NET. Esto reduce el tamaño del archivo PDF generado. Siga los pasos a continuación:

## Paso 1: Cargar el documento

Comience cargando el documento que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento.

## Paso 2: Configure las opciones de guardado de PDF

Cree una instancia de la clase PdfSaveOptions y establezca las opciones de reducción de escala de la imagen:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 El`Resolution` propiedad especifica la resolución de destino de las imágenes y la`ResolutionThreshold` La propiedad especifica la resolución mínima por debajo de la cual las imágenes no se reducirán.

## Paso 3: Convertir documento a PDF

 Utilizar el`Save` método para convertir el documento a PDF especificando las opciones de guardado:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Código fuente de ejemplo para reducción de resolución de imágenes usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//Podemos establecer un umbral mínimo para la reducción de resolución.
	// Este valor evitará que se reduzca la resolución de la segunda imagen en el documento de entrada.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Siguiendo estos pasos, puede reducir fácilmente la resolución de la imagen al convertir a PDF con Aspose.Words para .NET.


