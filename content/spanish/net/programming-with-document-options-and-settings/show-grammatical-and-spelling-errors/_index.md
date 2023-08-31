---
title: Mostrar errores gramaticales y ortográficos
linktitle: Mostrar errores gramaticales y ortográficos
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para habilitar la visualización de errores gramaticales y ortográficos en un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

En este tutorial, lo guiaremos a través del código fuente de C# para habilitar la visualización de errores gramaticales y ortográficos con Aspose.Words para .NET. Esta función le permite ver errores gramaticales y ortográficos en un documento.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento de Word cuyo mensaje queremos mostrar errores gramaticales y ortográficos. Utilice el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: habilitar la visualización de errores

Ahora habilitaremos la visualización de errores gramaticales y ortográficos en el documento. Utilice el siguiente código para habilitar la visualización de errores:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Este código permite la visualización de errores gramaticales (`ShowGrammaticalErrors`) y errores ortográficos (`ShowSpellingErrors`) en el documento.

### Código fuente de ejemplo para mostrar errores gramaticales y ortográficos usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo habilitar la visualización de errores gramaticales y ortográficos en un documento usando Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, puede habilitar fácilmente esta función en sus propios documentos.