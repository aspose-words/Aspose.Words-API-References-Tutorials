---
title: Establecer configuración de página y formato de sección
linktitle: Establecer configuración de página y formato de sección
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para configurar el diseño y el formato de sección de un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

En este tutorial, lo guiaremos a través del código fuente de C# para configurar el diseño y el formato de sección con Aspose.Words para .NET. Esta función le permite configurar la orientación de la página, los márgenes y el tamaño del papel.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: crear el documento

En este paso, crearemos un nuevo documento. Utilice el siguiente código para crear el documento e inicializar el constructor:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde desea guardar el documento.

## Paso 3: configurar el diseño y guardar el documento

Ahora configuremos el diseño del documento. Utilice el siguiente código para establecer la orientación, los márgenes y el tamaño del papel:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Este código establecerá la orientación de la página en horizontal, el margen izquierdo en 50 y el tamaño del papel en 10x14.

### Código fuente de ejemplo para configurar la configuración de página y el formato de sección usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

Asegúrese de especificar la ruta correcta al directorio donde desea guardar el documento en el`dataDir` variable.

Ahora ha aprendido cómo configurar el diseño y el formato de sección de un documento usando Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, podrá personalizar fácilmente el diseño y el formato de sus propios documentos.