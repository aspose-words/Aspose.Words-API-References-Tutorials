---
title: Mostrar errores gramaticales y ortográficos
linktitle: Mostrar errores gramaticales y ortográficos
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para habilitar la visualización de errores gramaticales y ortográficos en un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

En este tutorial, lo guiaremos a través del código fuente de C# para habilitar la visualización de errores gramaticales y ortográficos con Aspose.Words para .NET. Esta característica le permite ver errores gramaticales y ortográficos en un documento.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Cargar el documento

En este paso, cargaremos el documento de Word para el que queremos mostrar errores gramaticales y ortográficos. Use el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: habilite la visualización de errores

Ahora habilitaremos la visualización de errores gramaticales y ortográficos en el documento. Use el siguiente código para habilitar la visualización de errores:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Este código permite la visualización de errores gramaticales (`ShowGrammaticalErrors`) y faltas de ortografía (`ShowSpellingErrors`) en el documento.

### Ejemplo de código fuente para Mostrar errores gramaticales y ortográficos usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo habilitar la visualización de errores gramaticales y ortográficos en un documento usando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede habilitar fácilmente esta función en sus propios documentos.