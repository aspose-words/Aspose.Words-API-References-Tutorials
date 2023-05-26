---
title: Todas las fuentes incrustadas
linktitle: Todas las fuentes incrustadas
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para incrustar todas las fuentes en un PDF usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función de todas las fuentes incrustadas de Aspose.Words para .NET. Revisaremos el fragmento de código y explicaremos cada parte en detalle. Al final de este tutorial, podrá comprender cómo incrustar todas las fuentes en un documento y generar un PDF con las fuentes incrustadas utilizando Aspose.Words para .NET.

Antes de comenzar, asegúrese de tener instalada y configurada la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir la ruta del directorio del documento

Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Rendering.docx" y se encuentra en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: Configure las opciones de guardado de PDF

 Para incrustar todas las fuentes en el PDF resultante, necesitamos configurar el`PdfSaveOptions` objeto con el`EmbedFullFonts` propiedad establecida en`true`. Esto garantiza que todas las fuentes utilizadas en el documento se incluyan en el archivo PDF generado.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## Paso 4: Guarde el documento como PDF con fuentes incrustadas

 Finalmente, podemos guardar el documento como un archivo PDF con las fuentes incrustadas. Especifique el nombre del archivo de salida y el`saveOptions` objeto que configuramos en el paso anterior.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

¡Eso es todo! Ha incrustado con éxito todas las fuentes en un documento y ha generado un PDF con las fuentes incrustadas utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para Embedded All Fonts usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// El PDF de salida se incrustará con todas las fuentes que se encuentran en el documento.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## Conclusión

En este tutorial, hemos cubierto el proceso paso a paso del uso de la característica Embedded All Fonts de Aspose.Words para .NET. Aprendimos cómo cargar un documento, configurar las opciones de guardado de PDF y guardar el documento como un archivo PDF con fuentes incrustadas. Al seguir esta guía, puede asegurarse de que sus documentos PDF tengan todas las fuentes necesarias incrustadas, lo que brinda una representación uniforme y precisa en diferentes dispositivos y plataformas.
