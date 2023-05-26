---
title: Saltar fuentes incrustadas Arial y Times Roman
linktitle: Saltar fuentes incrustadas Arial y Times Roman
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para generar PDF sin incrustar fuentes Arial y Times Roman con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Este artículo proporciona una guía paso a paso sobre cómo utilizar la función para pasar las fuentes incrustadas Arial y Times Roman al tamaño de un metarchivo con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo configurar la opción de modo de incrustación de fuentes en un documento y generar un PDF sin incrustar fuentes Arial y Times Roman.

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

## Paso 3: configure las opciones de guardar como PDF con incrustación de fuentes

 Para omitir la incrustación de fuentes Arial y Times Roman en el PDF generado, debemos configurar el`PdfSaveOptions` objeto y establecer el`FontEmbeddingMode` propiedad a`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Paso 4: Guarde el documento como PDF sin fuentes incrustadas

Finalmente, podemos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Eso es todo ! Ha generado correctamente un PDF sin incrustar fuentes Arial y Times Roman con Aspose.Words para .NET.

### Ejemplo de código fuente para omitir las fuentes incrustadas Arial y Times Roman en tamaño de metarchivo con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```
