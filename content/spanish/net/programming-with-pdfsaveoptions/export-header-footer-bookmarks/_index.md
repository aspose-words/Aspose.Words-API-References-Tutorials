---
title: Exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF
linktitle: Exportar marcadores de encabezado y pie de página de un documento de Word a un documento PDF
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a exportar marcadores de encabezado y pie de página de un documento de Word a PDF usando Aspose.Words para .NET con nuestra guía paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---
## Introducción

Convertir documentos de Word a PDF es una tarea común, especialmente cuando desea compartir o archivar documentos conservando su formato. A veces, estos documentos contienen marcadores importantes en los encabezados y pies de página. En este tutorial, recorreremos el proceso de exportar estos marcadores de un documento de Word a un PDF usando Aspose.Words para .NET.

## Requisitos previos

Antes de sumergirnos, asegúrese de tener lo siguiente:

- Aspose.Words para .NET: Debe tener instalado Aspose.Words para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: configure su entorno de desarrollo. Puede utilizar Visual Studio o cualquier otro IDE compatible con .NET.
- Conocimientos básicos de C#: se requiere familiaridad con la programación de C# para seguir los ejemplos de código.

## Importar espacios de nombres

Lo primero es lo primero: debe importar los espacios de nombres necesarios en su proyecto C#. Agregue estas líneas en la parte superior de su archivo de código:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Dividamos el proceso en pasos fáciles de seguir.

## Paso 1: Inicializar el documento

El primer paso es cargar su documento de Word. Así es como puedes hacerlo:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

En este paso, simplemente especificará la ruta a su directorio de documentos y cargará el documento de Word.

## Paso 2: configurar las opciones de guardar PDF

A continuación, debe configurar las opciones de guardado de PDF para asegurarse de que los marcadores en los encabezados y pies de página se exporten correctamente.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

 Aquí estamos configurando el`PdfSaveOptions` . El`DefaultBookmarksOutlineLevel` La propiedad establece el nivel de contorno de los marcadores y el`HeaderFooterBookmarksExportMode` La propiedad garantiza que solo se exporte la primera aparición de marcadores en encabezados y pies de página.

## Paso 3: guarde el documento como PDF

Finalmente, guarde su documento como PDF con las opciones configuradas.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

En este paso, guardará el documento en la ruta especificada con las opciones que ha configurado.

## Conclusión

¡Y ahí lo tienes! Si sigue estos pasos, puede exportar fácilmente marcadores de los encabezados y pies de página de un documento de Word a un PDF usando Aspose.Words para .NET. Este método garantiza que las ayudas de navegación importantes dentro de su documento se conserven en formato PDF, lo que facilita a los lectores la navegación por su documento.

## Preguntas frecuentes

### ¿Puedo exportar todos los marcadores del documento de Word a PDF?

 Sí tu puedes. En el`PdfSaveOptions`, puede ajustar la configuración para incluir todos los marcadores si es necesario.

### ¿Qué pasa si también quiero exportar marcadores del cuerpo del documento?

 Puedes configurar el`OutlineOptions` en`PdfSaveOptions` para incluir marcadores del cuerpo del documento.

### ¿Es posible personalizar los niveles de marcadores en el PDF?

 ¡Absolutamente! Puedes personalizar el`DefaultBookmarksOutlineLevel` propiedad para establecer diferentes niveles de contorno para sus marcadores.

### ¿Cómo manejo documentos sin marcadores?

Si su documento no tiene marcadores, el PDF se generará sin ningún contorno de marcador. Asegúrese de que su documento contenga marcadores si los necesita en el PDF.

### ¿Puedo utilizar este método para otros tipos de documentos como DOCX o RTF?

Sí, Aspose.Words para .NET admite varios tipos de documentos, incluidos DOCX, RTF y otros.