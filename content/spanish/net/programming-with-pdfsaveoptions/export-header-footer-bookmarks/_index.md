---
title: Exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF
linktitle: Exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para exportar marcadores de encabezado y pie de página de documentos de Word a marcadores de documentos PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Este artículo proporciona una guía paso a paso sobre cómo exportar marcadores de pie de página de encabezado de documento de Word a la función de documento pdf con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo exportar marcadores de encabezados y pies de página de un documento y generar un PDF con los marcadores apropiados.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Marcadores en encabezados y pies de página.docx" y está ubicado en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Paso 3: Configurar las opciones de guardar como PDF

 Para exportar marcadores de encabezado y pie de página, necesitamos configurar el`PdfSaveOptions` objeto. En este ejemplo, configuramos el nivel de esquema de marcador predeterminado en 1 y el modo de exportación de marcadores de encabezado y pie de página en "Primero".

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Paso 4: guarde el documento como PDF con marcadores de encabezados y pies de página

Finalmente podremos guardar el documento en formato PDF utilizando las opciones de guardado configuradas previamente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Eso es todo ! Ha exportado correctamente los marcadores de encabezado y pie de página de un documento y ha generado un PDF con los marcadores adecuados utilizando Aspose.Words para .NET.

### Código fuente de muestra para exportar marcadores de encabezado y pie de página con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Conclusión

En este tutorial, explicamos cómo exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF usando Aspose.Words para .NET. Los marcadores exportados permiten una navegación sencilla y una referencia rápida a los encabezados y pies de página correspondientes en el documento PDF generado. Siga los pasos descritos para exportar marcadores de encabezado y pie de página de un documento y generar un PDF con los marcadores apropiados usando Aspose.Words para .NET. Asegúrese de especificar la ruta correcta a sus documentos y configurar las opciones de guardado según sea necesario.

### Preguntas frecuentes

### P: ¿Qué significa exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF?
R: Exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF es una función para mantener y generar marcadores en el documento PDF a partir de los encabezados y pies de página. pies de página del documento original de Word. Esto permite a los usuarios navegar rápida y fácilmente por el documento PDF utilizando marcadores correspondientes a encabezados y pies de página.

### P: ¿Cómo puedo usar Aspose.Words para .NET para exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF?
R: Para exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF usando Aspose.Words para .NET, siga estos pasos:

 Establezca la ruta del directorio donde se encuentran sus documentos reemplazando`"YOUR DOCUMENT DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento que desea procesar utilizando el`Document` clase y especifique la ruta al documento de Word en el directorio de documentos especificado.

 Configure las opciones de guardar como PDF creando una instancia del`PdfSaveOptions` clase y configurar las opciones apropiadas de marcador de encabezado y pie de página.

 Guarde el documento en formato PDF utilizando el`Save` método de la`Document` clase que especifica la ruta y las opciones de guardado.

### P: ¿Cuáles son los beneficios de exportar marcadores de encabezado y pie de página a un documento PDF?
R: Las ventajas de exportar marcadores de encabezado y pie de página a un documento PDF son:

Navegación sencilla: los marcadores permiten a los usuarios navegar fácilmente en un documento PDF haciendo referencia a encabezados y pies de página específicos.

Referencia rápida: los marcadores permiten a los usuarios encontrar rápidamente secciones relevantes del documento PDF según los encabezados y pies de página.