---
title: Convertir documento de Word a PDF 1.7
linktitle: Convertir documento de Word a PDF 1.7
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a convertir documentos de Word a PDF 1.7 con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

En este tutorial, lo guiaremos a través de los pasos para convertir un documento de Word a PDF 1.7 con Aspose.Words para .NET. La conversión a PDF 1.7 le permite generar archivos PDF que cumplen con el estándar PDF 1.7. Siga los pasos a continuación:

## Paso 1: cargar el documento

Comience cargando el documento que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento.

## Paso 2: configurar las opciones de conversión de PDF

Cree una instancia de la clase PdfSaveOptions y especifique la versión del estándar PDF que desea utilizar:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Esta opción garantiza que el archivo PDF generado cumpla con el estándar PDF 1.7.

## Paso 3: convertir documento a PDF

 Utilizar el`Save` Método para convertir el documento a PDF especificando las opciones de conversión:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Código fuente de ejemplo para la conversión a PDF 17 usando Aspose.Words para .NET

Aquí está el código fuente completo para convertir a PDF 1.7 con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Siguiendo estos pasos, podrá convertir fácilmente a PDF 1.7 con Aspose.Words para .NET.


## Conclusión

En este tutorial, explicamos cómo convertir un documento de Word a PDF 1.7 usando Aspose.Words para .NET. Siguiendo los pasos descritos, podrá generar fácilmente archivos PDF que cumplan con el estándar PDF 1.7. Asegúrese de especificar la ruta correcta a su documento de Word y configure las opciones para convertir a PDF según sea necesario. La conversión a PDF 1.7 garantiza una compatibilidad y legibilidad óptimas en diferentes plataformas.

### Preguntas frecuentes

#### P: ¿Qué es la conversión de Word a PDF 1.7?
R: Convertir documentos de Word a PDF 1.7 consiste en generar archivos PDF que cumplan con el estándar PDF 1.7. Este estándar especifica características y requisitos para archivos PDF, lo que permite una compatibilidad y legibilidad óptimas en diferentes plataformas.

#### P: ¿Cómo puedo convertir un documento de Word a PDF 1.7 usando Aspose.Words para .NET?
R: Para convertir un documento de Word a PDF 1.7 usando Aspose.Words para .NET, siga estos pasos:

 Establezca la ruta del directorio donde se encuentran sus documentos reemplazando`"YOUR DOCUMENTS DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento de Word que desea convertir a PDF usando el`Document` clase y especifique la ruta al documento de Word en el directorio de documentos especificado.

 Configure la conversión como opciones de PDF creando una instancia del`PdfSaveOptions`clase y especificando la versión del estándar PDF que desea utilizar utilizando el`Compliance` propiedad con el valor`PdfCompliance. Pdf17` para generar un archivo PDF que cumpla con el estándar PDF 1.7.

 Guarde el documento en formato PDF utilizando el`Save` método de la`Document` clase que especifica la ruta y las opciones de guardado.

#### P: ¿Cuáles son los beneficios de convertir a PDF 1.7 con Aspose.Words para .NET?
R: Las ventajas de convertir a PDF 1.7 con Aspose.Words para .NET son:

Compatible con PDF 1.7: la conversión a PDF 1.7 garantiza que el archivo PDF generado sea compatible con PDF 1.7, lo que garantiza compatibilidad y legibilidad en diferentes plataformas.

Preservación del formato del documento: Aspose.Words para .NET garantiza una conversión precisa de documentos de Word al preservar el formato, las imágenes y los estilos, lo que da como resultado un archivo PDF fiel al original.