---
title: Actualizar la última propiedad impresa en un documento PDF
linktitle: Actualizar la última propiedad impresa en un documento PDF
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para actualizar la propiedad "Última impresión" al convertir a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Este artículo proporciona una guía paso a paso sobre cómo utilizar la propiedad "Última impresión" en la función de actualización de documentos PDF con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo configurar la opción para actualizar la propiedad "Última impresión" al convertir a PDF.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Rendering.docx" y está ubicado en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: Configure las opciones de Guardar como PDF con la propiedad "Última impresión" actualizada

 Para habilitar la actualización de la propiedad "Última impresión" al convertir a PDF, debemos configurar el`PdfSaveOptions` objeto y establecer el`UpdateLastPrintedProperty` propiedad a`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Paso 4: guarde el documento como PDF con la actualización de la propiedad "Última impresión"

Finalmente podremos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Eso es todo ! Ha habilitado con éxito la actualización de la propiedad "Última impresión" al convertir un documento a PDF usando Aspose.Words para .NET.

### Código fuente de ejemplo para actualizar la propiedad "Última impresión" con Aspose.Words para .NET


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Conclusión

En este tutorial, explicamos cómo actualizar la propiedad "Última impresión" en un documento PDF usando Aspose.Words para .NET. Siguiendo los pasos indicados, puede configurar fácilmente la opción para actualizar la propiedad "Última impresión" al convertir un documento a PDF. Utilice esta función para realizar un seguimiento del uso de los documentos y la información relacionada.

### Preguntas frecuentes

#### P: ¿Qué es la propiedad "Última impresión" en un documento PDF?
R: La propiedad "Última impresión" en un documento PDF se refiere a la fecha y hora en que se imprimió el documento por última vez. Esta propiedad puede resultar útil para realizar un seguimiento de información sobre el uso y la gestión de documentos.

#### P: ¿Cómo puedo actualizar la propiedad "Última impresión" en un documento PDF con Aspose.Words para .NET?
R: Para actualizar la propiedad "Última impresión" en un documento PDF con Aspose.Words para .NET, siga estos pasos:

 Crear una instancia del`Document` clase que especifica la ruta al documento de Word.

 Crear una instancia del`PdfSaveOptions` clase y establecer el`UpdateLastPrintedProperty` propiedad a`true` para permitir la actualización de la propiedad "Última impresión".

 Utilizar el`Save` método de la`Document`clase para guardar el documento en formato PDF especificando opciones de guardado.

#### P: ¿Cómo puedo verificar si la propiedad "Última impresión" se actualizó en el documento PDF generado?
R: Puede verificar si la propiedad "Última impresión" se actualizó en el documento PDF generado abriendo el archivo PDF con un visor de PDF compatible, como Adobe Acrobat Reader, y viendo la información del documento. La fecha y hora de la última impresión deben corresponder a la fecha y hora de generación del documento PDF.
