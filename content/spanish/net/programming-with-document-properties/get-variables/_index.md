---
title: Obtener variables
linktitle: Obtener variables
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para recuperar variables de documentos con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/get-variables/
---

En este tutorial, lo guiaremos a través del código fuente de C# para recuperar variables de un documento con Aspose.Words para .NET. Esta característica le permite acceder a variables definidas en un documento.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento

En este paso, cargaremos el documento de Word del cual queremos recuperar las variables. Utilice el siguiente código para cargar el documento:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Reemplazar`"YOUR DOCUMENTS DIRECTORY"` con la ruta real del directorio donde se encuentra su documento.

## Paso 3: Recuperar variables

Ahora recuperaremos las variables definidas en el documento. Utilice el siguiente código:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Este código itera sobre cada par clave-valor en las variables del documento y recupera el nombre y el valor de cada variable. Luego, las variables se concatenan para mostrar la información de cada variable.

### Código fuente de ejemplo para Obtener variables usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Asegúrese de especificar la ruta correcta del documento en el`dataDir` variable.

Ahora ha aprendido cómo recuperar variables de un documento usando Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, podrá acceder y ver fácilmente las variables de sus propios documentos.