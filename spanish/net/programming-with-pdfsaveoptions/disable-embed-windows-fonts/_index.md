---
title: Deshabilitar incrustar fuentes de Windows
linktitle: Deshabilitar incrustar fuentes de Windows
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a deshabilitar la incrustación de fuentes de Windows al convertir documentos a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

En este tutorial, lo guiaremos a través de los pasos para deshabilitar la incrustación de fuentes de Windows en un documento PDF con Aspose.Words para .NET. Al deshabilitar la incrustación de fuentes, puede reducir el tamaño del archivo PDF generado. Siga los pasos a continuación:

## Paso 1: Cargar el documento

Comience cargando el documento que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento.

## Paso 2: Configure las opciones de guardado de PDF

Cree una instancia de la clase PdfSaveOptions y especifique cómo incrustar fuentes:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Esta opción le permite desactivar la integración de fuentes de Windows en el archivo PDF generado.

## Paso 3: Convertir documento a PDF

 Utilizar el`Save` método para convertir el documento a PDF especificando las opciones de conversión:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Código fuente de ejemplo para deshabilitar fuentes de Windows incrustadas usando Aspose.Words para .NET

Aquí está el código fuente completo para deshabilitar la incrustación de fuentes de Windows en un documento PDF con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// El PDF de salida se guardará sin incrustar las fuentes estándar de Windows.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Siguiendo estos pasos, puede deshabilitar fácilmente la incrustación de fuentes de Windows en un documento PDF con Aspose.Words para .NET.

