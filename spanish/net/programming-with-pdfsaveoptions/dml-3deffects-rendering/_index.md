---
title: Representación Dml 3DEffects
linktitle: Representación Dml 3DEffects
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a habilitar la representación de efectos DML 3D al convertir a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

En este tutorial, lo guiaremos a través de los pasos para habilitar la representación de efectos 3D DML al convertir a PDF con Aspose.Words para .NET. Esto mantiene los efectos 3D en el documento PDF generado. Siga los pasos a continuación:

## Paso 1: Cargar el documento

Comience cargando el documento que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento.

## Paso 2: Configure las opciones de guardado de PDF

Cree una instancia de la clase PdfSaveOptions y habilite la representación avanzada de efectos 3D DML:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Esta opción mantiene los efectos 3D en el documento PDF generado.

## Paso 3: Convertir documento a PDF

 Utilizar el`Save` método para convertir el documento a PDF especificando las opciones de guardado:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Ejemplo de código fuente para Dml 3DEffects Rendering usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Siguiendo estos pasos, puede habilitar fácilmente la representación de efectos DML 3D al convertir a PDF con Aspose.Words para .NET.



