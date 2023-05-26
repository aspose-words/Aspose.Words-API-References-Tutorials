---
title: Evite incrustar fuentes principales
linktitle: Evite incrustar fuentes principales
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a evitar la incrustación básica de fuentes al convertir documentos de Word a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

En este tutorial, lo guiaremos a través de los pasos para usar la función Evite la incrustación de fuentes básicas con Aspose.Words para .NET. Esta función le permite controlar si se deben incrustar fuentes básicas como Arial, Times New Roman, etc. en el PDF al convertir un documento de Word. Siga los pasos a continuación:

## Paso 1: Cargar el documento

Comience cargando el documento de Word que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento de Word.

## Paso 2: establezca las opciones de conversión de PDF

Cree una instancia de la clase PdfSaveOptions y habilite la prevención básica de la incrustación de fuentes:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Esta opción controla si las fuentes base deben incrustarse en el PDF o no.

## Paso 3: Convertir documento a PDF

 Utilizar el`Save` método para convertir el documento de Word a PDF especificando las opciones de conversión:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Ejemplo de código fuente para evitar incrustar fuentes principales usando Aspose.Words para .NET

Aquí está el código fuente completo para usar la función para evitar la incrustación de fuentes principales con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// El PDF de salida no se incrustará con fuentes principales como Arial, Times New Roman, etc.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Siguiendo estos pasos, puede controlar fácilmente si las fuentes base deben incrustarse en el PDF al convertir un documento de Word con Aspose.Words para .NET.

