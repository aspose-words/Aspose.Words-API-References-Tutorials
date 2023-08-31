---
title: Renderizar efectos 3D DML 3D en un documento PDF
linktitle: Renderizar efectos 3D DML 3D en un documento PDF
second_title: API de procesamiento de documentos de Aspose.Words
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

## Conclusión

En este tutorial, explicamos cómo habilitar la representación de efectos DML 3D al convertir a PDF con Aspose.Words para .NET. Siguiendo los pasos descritos, puede mantener fácilmente los efectos 3D en el documento PDF generado. Utilice esta función para conservar los efectos visuales importantes de su documento original.


### Preguntas frecuentes

#### P: ¿Qué es la representación de efectos DML 3D en un documento PDF?
R: La representación de efectos DML 3D en un documento PDF se refiere a la capacidad de conservar los efectos 3D al convertir un documento a formato PDF. Esto conserva los efectos visuales y asegura que el documento PDF generado se vea como el documento original.

#### P: ¿Cómo puedo habilitar la representación de efectos DML 3D al convertir a PDF con Aspose.Words para .NET?
R: Para habilitar la representación de efectos DML 3D al convertir a PDF con Aspose.Words para .NET, siga estos pasos:

 Crear una instancia de la`Document` class especificando la ruta al documento de Word.

 Crear una instancia de la`PdfSaveOptions`clase y establecer el`Dml3DEffectsRenderingMode` propiedad a`Dml3DEffectsRenderingMode.Advanced` para habilitar la renderización avanzada de efectos 3D DML.

 Utilizar el`Save` metodo de la`Document`class para guardar el documento en formato PDF especificando las opciones de guardado.

#### P: ¿Cómo puedo comprobar si se han renderizado efectos DML 3D en el documento PDF generado?
R: Para comprobar si los efectos DML 3D se han representado en el documento PDF generado, abra el archivo PDF con un visor de PDF compatible, como Adobe Acrobat Reader, y examine el documento. Debería ver los efectos 3D tal como aparecen en el documento original.



