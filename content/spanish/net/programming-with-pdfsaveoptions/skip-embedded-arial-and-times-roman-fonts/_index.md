---
title: Optimice el tamaño de PDF con Skip Embedded Arial y Times Roman Fonts
linktitle: Optimice el tamaño de PDF con Skip Embedded Arial y Times Roman Fonts
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para generar PDF optimizados sin incrustar fuentes Arial y Times Roman con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Este artículo proporciona una guía paso a paso sobre cómo utilizar la función para optimizar el tamaño de PDF omitiendo las fuentes incrustadas Arial y Times Roman al tamaño de metarchivo con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo configurar la opción de modo de incrustación de fuentes en un documento y generar un PDF sin incrustar fuentes Arial y Times Roman.

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

## Conclusión

En este tutorial, explicamos cómo deshabilitar la incrustación de fuentes Arial y Times Roman en un documento PDF usando Aspose.Words para .NET. Siguiendo los pasos descritos, puede generar un archivo PDF sin incrustar estas fuentes específicas, lo que puede ayudar a reducir el tamaño del archivo y garantizar una mejor compatibilidad de documentos en diferentes plataformas. Asegúrese de considerar las consecuencias de deshabilitar la incrustación de fuentes al usar esta función. Siéntase libre de explorar más funciones de Aspose.Words para .NET para optimizar la generación de sus archivos PDF.

### Preguntas frecuentes

#### P: ¿Qué es deshabilitar la incrustación de fuentes Arial y Times Roman en un documento PDF y por qué es importante?
R: Deshabilitar la incrustación de fuentes Arial y Times Roman en un documento PDF es el proceso de no incluir estas fuentes en el archivo PDF generado. Esto puede ser importante para reducir el tamaño del archivo PDF al evitar incluir fuentes que ya están comúnmente disponibles en los sistemas de lectura de PDF. También puede ayudar a garantizar una mejor compatibilidad y una apariencia uniforme del documento PDF en diferentes dispositivos y plataformas.

#### P: ¿Cómo puedo configurar Aspose.Words para .NET para que no incruste fuentes Arial y Times Roman en un documento PDF?
R: Para configurar Aspose.Words para .NET para que no incruste fuentes Arial y Times Roman en un documento PDF, siga estos pasos:

 Establezca la ruta del directorio donde se encuentran sus documentos reemplazando`"YOUR DOCUMENT DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento que desea procesar utilizando el`Document` clase y la ruta del documento especificado.

 Crear una instancia de la`PdfSaveOptions`clase y establecer el`FontEmbeddingMode` propiedad a`PdfFontEmbeddingMode.EmbedAll`. Esto incrustará todas las fuentes excepto Arial y Times Roman en el archivo PDF generado.

 Utilizar el`Save` metodo de la`Document` objeto para guardar el documento en formato PDF especificando las opciones de guardado configuradas anteriormente.

#### P: ¿Cuáles son los beneficios de deshabilitar la incrustación de fuentes Arial y Times Roman en un documento PDF?
R: Los beneficios de deshabilitar la incrustación de fuentes Arial y Times Roman en un documento PDF son:

Reducción del tamaño del archivo PDF: al evitar la incrustación de fuentes comúnmente disponibles como Arial y Times Roman, se puede reducir el tamaño del archivo PDF, lo que facilita el almacenamiento, el intercambio y la transferencia de archivos.

Mejor compatibilidad: al usar fuentes que están comúnmente disponibles en los sistemas de lectura de PDF, garantiza una mejor compatibilidad y apariencia del documento en diferentes dispositivos y plataformas.

#### P: ¿Cuáles son las consecuencias de deshabilitar la incrustación de fuentes Arial y Times Roman en un documento PDF?
R: Las consecuencias de deshabilitar la incrustación de fuentes Arial y Times Roman en un documento PDF son las siguientes:

Apariencia diferente: si las fuentes Arial y Times Roman no están disponibles en el sistema donde se abre el PDF, se utilizarán fuentes sustitutas, lo que puede dar como resultado una apariencia diferente a la prevista.

Problemas de legibilidad: las fuentes sustitutas utilizadas pueden no ser tan legibles como las fuentes originales, lo que puede afectar la legibilidad del documento.