---
title: Compresión de imagen
linktitle: Compresión de imagen
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para comprimir imágenes con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/image-compression/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función de compresión de imágenes con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo comprimir imágenes en un documento y generar un PDF con la compresión de imagen adecuada.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Rendering.docx" y se encuentra en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: configure las opciones de guardar como PDF con compresión de imágenes

 Para comprimir imágenes al convertir a PDF, necesitamos configurar el`PdfSaveOptions` objeto. Podemos configurar el tipo de compresión de imagen, la calidad JPEG y otras opciones de cumplimiento de PDF si es necesario.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Paso 4: Guarde el documento como PDF con compresión de imagen

Finalmente, podemos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Paso 5: configure las opciones para guardar en PDF/A-2u con compresión de imágenes

Si desea generar un PDF compatible con PDF/A-2u con compresión de imágenes, puede configurar las opciones de guardado adicionales.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Utilice la compresión JPEG con un 50 % de calidad para reducir el tamaño del archivo.
};
```

## Paso 6: Guarde el documento como PDF/A-2u con compresión de imagen

Guarde el documento en formato PDF/A-2u utilizando las opciones de guardado adicionales configuradas anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Eso es todo ! Comprimió con éxito las imágenes en un documento y generó un PDF con la compresión de imagen adecuada utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para comprimir imágenes con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Use compresión JPEG al 50% de calidad para reducir el tamaño del archivo.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```
