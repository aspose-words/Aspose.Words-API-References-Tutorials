---
title: Actualizar última propiedad impresa
linktitle: Actualizar última propiedad impresa
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para actualizar la propiedad "Última impresión" al convertir a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función de actualización de propiedades "Última impresión" con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo configurar la opción para actualizar la propiedad "Última impresión" al convertir a PDF.

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

## Paso 3: configure las opciones Guardar como PDF con la propiedad "Última impresión" actualizada

 Para habilitar la actualización de la propiedad "Última impresión" al convertir a PDF, debemos configurar el`PdfSaveOptions` objeto y establecer el`UpdateLastPrintedProperty` propiedad a`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Paso 4: Guarde el documento como PDF con la actualización de la propiedad "Última impresión"

Finalmente, podemos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Eso es todo ! Ha habilitado correctamente la actualización de la propiedad "Última impresión" al convertir un documento a PDF usando Aspose.Words para .NET.

### Ejemplo de código fuente para actualizar la propiedad "Última impresión" con Aspose.Words para .NET


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
