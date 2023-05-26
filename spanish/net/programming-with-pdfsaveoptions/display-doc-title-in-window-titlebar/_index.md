---
title: Mostrar el título del documento en la barra de título de la ventana
linktitle: Mostrar el título del documento en la barra de título de la ventana
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a mostrar el título del documento en la barra de título de la ventana al convertir a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

En este tutorial, lo guiaremos a través de los pasos para mostrar el título del documento en la barra de título de la ventana con Aspose.Words para .NET. Esta función le permite mostrar el título del documento en la barra de título de la ventana cuando abre el documento PDF generado. Siga los pasos a continuación:

## Paso 1: Cargar el documento

Comience cargando el documento que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento.

## Paso 2: configurar las opciones de guardado de PDF

Cree una instancia de la clase PdfSaveOptions y habilite la visualización del título del documento en la barra de título de la ventana:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Esta opción habilita la visualización del título del documento en la barra de título de la ventana al convertir a PDF.

## Paso 3: Convertir documento a PDF

 Utilizar el`Save` método para convertir el documento a PDF especificando las opciones de conversión:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Ejemplo de código fuente para mostrar el título del documento en la barra de título de la ventana usando Aspose.Words para .NET

Aquí está el código fuente completo para mostrar el título del documento en la barra de título de la ventana en un documento PDF con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
Siguiendo estos pasos, puede mostrar fácilmente el título del documento en la barra de título de la ventana al convertir a PDF con Aspose.Words para .NET.

