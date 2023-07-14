---
title: Exportar marcadores de pie de página de encabezado de documento de Word a documento PDF
linktitle: Exportar marcadores de pie de página de encabezado de documento de Word a documento PDF
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para exportar marcadores de pie de página de encabezado de documento de Word a marcadores de documento pdf con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Este artículo proporciona una guía paso a paso sobre cómo exportar marcadores de pie de página de encabezado de documento de Word a la función de documento PDF con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo exportar marcadores de encabezados y pies de página de un documento y generar un PDF con los marcadores apropiados.

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

## Conclusión

En este tutorial, explicamos cómo exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF usando Aspose.Words para .NET. Los marcadores exportados permiten una navegación fácil y una referencia rápida a los encabezados y pies de página correspondientes en el documento PDF generado. Siga los pasos descritos para exportar marcadores de encabezado y pie de página de un documento y generar un PDF con los marcadores apropiados usando Aspose.Words para .NET. Asegúrese de especificar la ruta correcta a sus documentos y configure las opciones de guardado según sea necesario.

# Preguntas frecuentes

### P: ¿Qué es exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF?
R: La exportación de marcadores de encabezado y pie de página de un documento de Word a un documento PDF es una función para mantener y generar marcadores en el documento PDF a partir de los encabezados y pies de página. pies de página del documento original de Word. Esto permite a los usuarios navegar rápida y fácilmente por el documento PDF mediante el uso de marcadores correspondientes a encabezados y pies de página.

### P: ¿Cómo puedo usar Aspose.Words para .NET para exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF?
R: Para exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF utilizando Aspose.Words para .NET, siga estos pasos:

 Establezca la ruta del directorio donde se encuentran sus documentos reemplazando`"YOUR DOCUMENT DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento que desea procesar utilizando el`Document` clase y especifique la ruta al documento de Word en el directorio de documentos especificado.

 Configure las opciones de guardar como PDF creando una instancia del`PdfSaveOptions` class y configurando las opciones apropiadas de marcador de encabezado y pie de página.

 Guarde el documento en formato PDF usando el`Save` metodo de la`Document`class especificando la ruta y las opciones de guardado.

### P: ¿Cuáles son los beneficios de exportar marcadores de encabezado y pie de página a un documento PDF?
R: Las ventajas de exportar marcadores de encabezado y pie de página a un documento PDF son:

Navegación sencilla: los marcadores permiten a los usuarios navegar fácilmente por un documento PDF haciendo referencia a encabezados y pies de página específicos.

Referencia rápida: los marcadores permiten a los usuarios encontrar rápidamente secciones relevantes del documento PDF en función de los encabezados y pies de página.