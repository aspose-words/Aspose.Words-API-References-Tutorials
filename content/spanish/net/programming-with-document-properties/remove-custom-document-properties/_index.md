---
title: Eliminar propiedades de documentos personalizados
linktitle: Eliminar propiedades de documentos personalizados
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para eliminar propiedades personalizadas de un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/remove-custom-document-properties/
---

En este tutorial, lo guiaremos a través del código fuente de C# para eliminar propiedades personalizadas de un documento con Aspose.Words para .NET. Esta característica le permite eliminar una propiedad personalizada específica de un documento.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento de Word del que queremos eliminar las propiedades personalizadas. Utilice el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: eliminar propiedades personalizadas

Ahora eliminemos una propiedad personalizada específica del documento. Utilice el siguiente código:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Este código elimina la propiedad personalizada "Fecha de autorización" del documento. Puede reemplazar "Fecha autorizada" con el nombre de la propiedad personalizada que desea eliminar.

### Código fuente de ejemplo para eliminar propiedades de documentos personalizados usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo eliminar propiedades personalizadas de un documento usando Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, puede eliminar fácilmente propiedades personalizadas de sus propios documentos.