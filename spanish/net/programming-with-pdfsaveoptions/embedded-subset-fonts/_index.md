---
title: Subconjunto de fuentes incrustadas
linktitle: Subconjunto de fuentes incrustadas
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para incrustar subconjuntos de fuentes en un PDF usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función de incrustación de subconjuntos de fuentes con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo incrustar subconjuntos de fuentes en un documento y generar un PDF que contenga solo los glifos utilizados en el documento.

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

## Paso 3: Configure las opciones de guardar como PDF

 Para crear un PDF que contenga solo los subconjuntos de fuentes utilizadas en el documento, debemos configurar el`PdfSaveOptions` objeto con el`EmbedFullFonts` propiedad establecida en`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Paso 4: Guarde el documento como PDF con subconjuntos de fuentes

 Finalmente, podemos guardar el documento como PDF usando los subconjuntos de fuentes. Especifique el nombre del archivo de salida y el`saveOptions` objeto que configuramos en el paso anterior.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Eso es todo ! Ha incrustado con éxito subconjuntos de fuentes en un documento y ha generado un PDF que contiene solo los glifos utilizados en el documento con Aspose.Words para .NET.

### Ejemplo de código fuente para incrustar subconjuntos de fuentes con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// El PDF de salida contendrá subconjuntos de las fuentes del documento.
	// Solo los glifos utilizados en el documento se incluyen en las fuentes PDF.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```
