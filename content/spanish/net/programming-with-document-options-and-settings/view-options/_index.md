---
title: Ver opciones
linktitle: Ver opciones
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para configurar las opciones de visualización de documentos con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/view-options/
---

En este tutorial, lo guiaremos a través del código fuente de C# para configurar las opciones de visualización con Aspose.Words para .NET. Esta función le permite personalizar el modo de visualización y el nivel de zoom en un documento.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso cargaremos el documento de Word para el que queremos configurar las opciones de visualización. Utilice el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: configurar las opciones de visualización

Ahora configuraremos las opciones de visualización del documento. Utilice el siguiente código para configurar el modo de visualización y el nivel de zoom:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Este código establece el modo de visualización en "Diseño de página" y el nivel de zoom en 50%.

### Código fuente de ejemplo para Ver opciones usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo configurar las opciones de visualización de documentos usando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, podrá personalizar fácilmente la visualización de sus propios documentos.