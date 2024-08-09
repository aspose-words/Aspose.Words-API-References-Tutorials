---
title: Guardar documentos como PDF en Aspose.Words para Java
linktitle: Guardar documentos como PDF
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda cómo guardar documentos de Word como PDF usando Aspose.Words para Java. Personalice fuentes, propiedades y calidad de imagen. Una guía completa para la conversión de PDF.
type: docs
weight: 22
url: /es/java/document-loading-and-saving/saving-documents-as-pdf/
---

## Introducción a guardar documentos como PDF en Aspose.Words para Java

En esta guía paso a paso, exploraremos cómo guardar documentos como PDF usando Aspose.Words para Java. Cubriremos varios aspectos de la conversión de PDF y proporcionaremos ejemplos de código para facilitar el proceso.

## Requisitos previos

Antes de comenzar, asegúrese de contar con los siguientes requisitos previos:

- Kit de desarrollo de Java (JDK) instalado en su sistema.
-  Aspose.Words para la biblioteca Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/words/java/).

## Convertir un documento a PDF

Para convertir un documento de Word a PDF, puede utilizar el siguiente fragmento de código:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Reemplazar`"input.docx"` con la ruta a su documento de Word y`"output.pdf"` con la ruta del archivo PDF de salida deseada.

## Controlar las opciones de guardar PDF

 Puede controlar varias opciones para guardar PDF utilizando el`PdfSaveOptions` clase. Por ejemplo, puede configurar el título de visualización del documento PDF de la siguiente manera:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## Incrustar fuentes en PDF

Para incrustar fuentes en el PDF generado, utilice el siguiente código:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## Personalizar las propiedades del documento

Puede personalizar las propiedades del documento en el PDF generado. Por ejemplo:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## Exportación de estructura de documento

 Para exportar la estructura del documento, establezca el`exportDocumentStructure` opción de`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## Compresión de imagen

Puede controlar la compresión de imágenes utilizando el siguiente código:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## Actualización de la última propiedad impresa

Para actualizar la propiedad "Última impresión" en el PDF, utilice:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## Representación de efectos DML 3D

Para una representación avanzada de efectos DML 3D, configure el modo de representación:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## Interpolando imágenes

Puede habilitar la interpolación de imágenes para mejorar la calidad de la imagen:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## Conclusión

Aspose.Words para Java proporciona capacidades integrales para convertir documentos de Word a formato PDF con opciones de flexibilidad y personalización. Puede controlar varios aspectos de la salida del PDF, incluidas las fuentes, las propiedades del documento, la compresión de imágenes y más.

## Preguntas frecuentes

### ¿Cómo convierto un documento de Word a PDF usando Aspose.Words para Java?

Para convertir un documento de Word a PDF, utilice el siguiente código:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Reemplazar`"input.docx"` con la ruta a su documento de Word y`"output.pdf"` con la ruta del archivo PDF de salida deseada.

### ¿Puedo incrustar fuentes en el PDF generado por Aspose.Words para Java?

 Sí, puede incrustar fuentes en el PDF configurando el`setEmbedFullFonts` opción de`true` en`PdfSaveOptions`. He aquí un ejemplo:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### ¿Cómo puedo personalizar las propiedades del documento en el PDF generado?

 Puede personalizar las propiedades del documento en el PDF usando el`setCustomPropertiesExport` opción en`PdfSaveOptions`. Por ejemplo:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### ¿Cuál es el propósito de la compresión de imágenes en Aspose.Words para Java?

 La compresión de imágenes le permite controlar la calidad y el tamaño de las imágenes en el PDF generado. Puede configurar el modo de compresión de imágenes usando`setImageCompression` en`PdfSaveOptions`.

### ¿Cómo actualizo la propiedad "Última impresión" en el PDF?

 Puede actualizar la propiedad "Última impresión" en el PDF configurando`setUpdateLastPrintedProperty` a`true` en`PdfSaveOptions`. Esto reflejará la última fecha de impresión en los metadatos del PDF.

### ¿Cómo puedo mejorar la calidad de la imagen al convertir a PDF?

 Para mejorar la calidad de la imagen, habilite la interpolación de imágenes configurando`setInterpolateImages` a`true` en`PdfSaveOptions`. Esto dará como resultado imágenes más fluidas y de mayor calidad en el PDF.