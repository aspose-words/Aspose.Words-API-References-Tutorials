---
title: Unir y anexar documentos en Aspose.Words para Java
linktitle: Unir y adjuntar documentos
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a unir y adjuntar documentos sin esfuerzo utilizando Aspose.Words para Java. Conserve el formato, administre encabezados, pies de página y más.
type: docs
weight: 30
url: /es/java/document-manipulation/joining-and-appending-documents/
---

## Introducción a unir y anexar documentos en Aspose.Words para Java

En este tutorial, exploraremos cómo unir y adjuntar documentos usando la biblioteca Aspose.Words para Java. Aprenderá cómo fusionar varios documentos sin problemas conservando el formato y la estructura.

## Requisitos previos

Antes de comenzar, asegúrese de tener configurada la API Aspose.Words para Java en su proyecto Java.

## Opciones de unión de documentos

### Anexar simple

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Agregar con opciones de formato de importación

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### Agregar a documento en blanco

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Agregar con conversión de número de página

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // Convertir campos NUMPAGES
dstDoc.updatePageLayout(); // Actualizar el diseño de la página para una numeración correcta
```

## Manejo de diferentes configuraciones de página

Al adjuntar documentos con diferentes configuraciones de página:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// Asegúrese de que la configuración de configuración de página coincida con el documento de destino
```

## Unir documentos con diferentes estilos

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## Comportamiento de estilo inteligente

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## Insertar documentos con DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Mantener la numeración de fuentes

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Manejo de cuadros de texto

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Administrar encabezados y pies de página

### Vincular encabezados y pies de página

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Desvincular encabezados y pies de página

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Conclusión

Aspose.Words para Java proporciona herramientas potentes y flexibles para unir y agregar documentos, ya sea que necesite mantener el formato, manejar diferentes configuraciones de página o administrar encabezados y pies de página. Experimente con estas técnicas para satisfacer sus necesidades específicas de procesamiento de documentos.

## Preguntas frecuentes

### ¿Cómo puedo unir documentos con diferentes estilos sin problemas?

 Para unir documentos con diferentes estilos, utilice`ImportFormatMode.USE_DESTINATION_STYLES` al agregar.

### ¿Puedo conservar la numeración de páginas al adjuntar documentos?

 Sí, puede conservar la numeración de páginas utilizando el`convertNumPageFieldsToPageRef` método y actualización del diseño de la página.

### ¿Qué es el comportamiento de estilo inteligente?

 Smart Style Behavior ayuda a mantener estilos consistentes al agregar documentos. Úselo con`ImportFormatOptions` para mejores resultados.

### ¿Cómo puedo manejar cuadros de texto al adjuntar documentos?

Colocar`importFormatOptions.setIgnoreTextBoxes(false)` para incluir cuadros de texto al agregar.

### ¿Qué pasa si quiero vincular/desvincular encabezados y pies de página entre documentos?

 Puede vincular encabezados y pies de página con`linkToPrevious(true)` o desvincularlos con`linkToPrevious(false)` según sea necesario.