---
title: Establecer configuración de página y formato de sección
linktitle: Establecer configuración de página y formato de sección
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para configurar el formato de la sección y el diseño de un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

En este tutorial, lo guiaremos a través del código fuente de C# para configurar el diseño y el formato de sección con Aspose.Words para .NET. Esta función le permite configurar la orientación de la página, los márgenes y el tamaño del papel.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Crear el documento

En este paso, crearemos un nuevo documento. Use el siguiente código para crear el documento e inicializar el constructor:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde desea guardar el documento.

## Paso 3: configurar el diseño y guardar el documento

Ahora vamos a configurar el diseño del documento. Utilice el siguiente código para establecer la orientación, los márgenes y el tamaño del papel:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Este código establecerá la orientación de la página en horizontal, el margen izquierdo en 50 y el tamaño del papel en 10x14.

### Ejemplo de código fuente para establecer la configuración de página y el formato de sección usando Aspose.Words para .NET

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

Ahora ha aprendido a configurar el diseño y el formato de sección de un documento utilizando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede personalizar fácilmente el diseño y el formato de sus propios documentos.