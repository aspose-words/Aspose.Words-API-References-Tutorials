---
title: Interpolar imágenes
linktitle: Interpolar imágenes
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para habilitar la interpolación de imágenes con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/interpolate-images/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función de interpolación de imágenes con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo habilitar la interpolación de imágenes al convertir a PDF.

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

## Paso 3: Configure las opciones para guardar como PDF con interpolación de cuadros

 Para habilitar la interpolación de imágenes al convertir a PDF, necesitamos configurar el`PdfSaveOptions` objeto configurando el`InterpolateImages` propiedad a`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };
```

## Paso 4: Guarde el documento como PDF con interpolación de cuadros

Finalmente, podemos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);
```

Eso es todo ! Ha habilitado con éxito la interpolación de imágenes al convertir un documento a PDF usando Aspose.Words para .NET.

### Ejemplo de código fuente para la interpolación de imágenes con Aspose.Words para .NET


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);

```
