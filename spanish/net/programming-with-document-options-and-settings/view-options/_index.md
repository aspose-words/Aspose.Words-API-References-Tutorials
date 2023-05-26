---
title: Ver opciones
linktitle: Ver opciones
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para configurar las opciones de visualización de documentos con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/view-options/
---

En este tutorial, lo guiaremos a través del código fuente de C# para configurar las opciones de visualización con Aspose.Words para .NET. Esta función le permite personalizar el modo de vista y el nivel de zoom en un documento.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Cargar el documento

En este paso cargaremos el documento de Word para el que queremos configurar las opciones de visualización. Use el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: Configuración de las opciones de visualización

Ahora configuraremos las opciones de visualización del documento. Use el siguiente código para configurar el modo de visualización y el nivel de zoom:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Este código establece el modo de vista en "PageLayout" y el nivel de zoom en 50%.

### Ejemplo de código fuente para Ver opciones usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido a configurar las opciones de visualización de documentos con Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede personalizar fácilmente la visualización de sus propios documentos.