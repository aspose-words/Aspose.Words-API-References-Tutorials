---
title: Eliminar propiedades de documentos personalizados
linktitle: Eliminar propiedades de documentos personalizados
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para eliminar propiedades personalizadas de un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/remove-custom-document-properties/
---

En este tutorial, lo guiaremos a través del código fuente de C# para eliminar propiedades personalizadas de un documento con Aspose.Words para .NET. Esta función le permite eliminar una propiedad personalizada específica de un documento.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Cargar el documento

En este paso, cargaremos el documento de Word del que queremos eliminar las propiedades personalizadas. Use el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: Eliminar propiedades personalizadas

Ahora eliminemos una propiedad personalizada específica del documento. Usa el siguiente código:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Este código elimina la propiedad personalizada "Fecha autorizada" del documento. Puede reemplazar "Fecha autorizada" con el nombre de la propiedad personalizada que desea eliminar.

### Ejemplo de código fuente para eliminar propiedades de documentos personalizados mediante Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido a eliminar propiedades personalizadas de un documento mediante Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede eliminar fácilmente las propiedades personalizadas de sus propios documentos.