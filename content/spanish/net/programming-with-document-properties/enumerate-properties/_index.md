---
title: Enumerar propiedades
linktitle: Enumerar propiedades
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para enumerar propiedades de documentos con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/enumerate-properties/
---

En este tutorial, lo guiaremos a través del código fuente de C# para enumerar las propiedades del documento con Aspose.Words para .NET. Esta función le permite acceder a las propiedades integradas y personalizadas de un documento.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento de Word cuyas propiedades queremos enumerar. Utilice el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: enumerar propiedades

Ahora enumeremos las propiedades del documento, tanto las integradas como las personalizadas. Utilice el siguiente código:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Este código muestra el nombre del documento y luego enumera las propiedades integradas y personalizadas que muestran su nombre y valor.

### Código fuente de ejemplo para enumerar propiedades usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido a enumerar las propiedades de un documento utilizando Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, podrá acceder y ver fácilmente las propiedades de sus propios documentos.

