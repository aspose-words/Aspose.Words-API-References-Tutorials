---
title: Agregar propiedades de documento personalizadas
linktitle: Agregar propiedades de documento personalizadas
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para agregar propiedades personalizadas a un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/add-custom-document-properties/
---

En este tutorial, lo guiaremos a través del código fuente de C# para agregar propiedades personalizadas a un documento con Aspose.Words para .NET. Esta característica le permite agregar información personalizada al documento.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento de Word al que queremos agregar propiedades personalizadas. Utilice el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: agregar propiedades personalizadas

Ahora agreguemos propiedades personalizadas al documento. Utilice el siguiente código para agregar las propiedades:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Este código primero verifica si la propiedad "Autorizado" ya existe en las propiedades personalizadas. Si existe, el proceso se interrumpe. De lo contrario, las propiedades personalizadas se agregan al documento.

### Código fuente de ejemplo para Agregar propiedades de documento personalizadas usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo agregar propiedades personalizadas a un documento usando Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, puede agregar fácilmente sus propias propiedades personalizadas a sus documentos.