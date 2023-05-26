---
title: Estructura del documento de exportación
linktitle: Estructura del documento de exportación
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para exportar la estructura de un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/export-document-structure/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función Exportar estructura del documento con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo exportar la estructura de un documento y generar un PDF con la estructura del documento visible.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Paragraphs.docx" y se encuentra en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Paso 3: Configure las opciones de guardar como PDF

 Para exportar la estructura del documento y hacer que la estructura sea visible en el panel de navegación "Contenido" de Adobe Acrobat Pro mientras se edita el archivo PDF, debemos configurar el`PdfSaveOptions` objeto con el`ExportDocumentStructure` propiedad establecida en`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Paso 4: Guarde el documento como PDF con la estructura del documento

Finalmente, podemos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

Eso es todo ! Exportó con éxito una estructura de documento y generó un PDF con la estructura del documento visible usando Aspose.Words para .NET.

### Ejemplo de código fuente para exportar la estructura del documento con Aspose.Words para .NET


```csharp

            // La ruta al directorio de documentos.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // El tamaño del archivo aumentará y la estructura será visible en el panel de navegación "Contenido".
            // de Adobe Acrobat Pro, mientras edita el .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```
