---
title: Exportar marcadores de encabezado y pie de página
linktitle: Exportar marcadores de encabezado y pie de página
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para exportar marcadores de encabezado y pie de página con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Este artículo proporciona una guía paso a paso sobre cómo usar la función Exportar marcadores de encabezado y pie de página con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo exportar marcadores de encabezados y pies de página de un documento y generar un PDF con los marcadores apropiados.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Marcadores en encabezados y pies de página.docx" y se encuentra en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Paso 3: Configure las opciones de guardar como PDF

 Para exportar marcadores de encabezado y pie de página, debemos configurar el`PdfSaveOptions` objeto. En este ejemplo, configuramos el nivel de esquema de marcador predeterminado en 1 y el modo de exportación de marcador de encabezado y pie de página en "Primero".

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Paso 4: guarde el documento como PDF con marcadores de encabezados y pies de página

Finalmente, podemos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Eso es todo ! Ha exportado con éxito los marcadores de encabezado y pie de página de un documento y ha generado un PDF con los marcadores apropiados utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para exportar marcadores de encabezado y pie de página con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```
