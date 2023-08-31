---
title: Configuración de página del documento
linktitle: Configuración de página del documento
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para configurar un diseño de documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/document-page-setup/
---

En este tutorial, lo guiaremos a través del código fuente de C# para configurar el diseño del documento con Aspose.Words para .NET. Esta función le permite configurar el modo de diseño, la cantidad de caracteres por línea y la cantidad de líneas por página.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso cargaremos el documento de Word que queremos configurar. Utilice el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: configurar el diseño

Ahora configuremos el diseño del documento. Utilice el siguiente código para configurar el modo de diseño, la cantidad de caracteres por línea y la cantidad de líneas por página:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Este código establece el modo de diseño en "Cuadrícula" y luego especifica el número de caracteres por línea y el número de líneas por página.

### Código fuente de ejemplo para configurar la página del documento usando Aspose.Words para .NET


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Establezca el modo de diseño para una sección que permita definir el comportamiento de la cuadrícula del documento.
	// Tenga en cuenta que la pestaña Cuadrícula del documento se vuelve visible en el cuadro de diálogo Configurar página de MS Word.
	// si algún idioma asiático se define como idioma de edición.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo configurar el diseño de un documento usando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, podrá personalizar fácilmente el diseño de sus propios documentos.