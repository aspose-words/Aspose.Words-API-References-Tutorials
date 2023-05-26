---
title: Búsqueda simple Reemplazar
linktitle: Búsqueda simple Reemplazar
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a realizar una búsqueda y reemplazo simple en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/find-and-replace-text/simple-find-replace/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función de búsqueda simple y reemplazo en la biblioteca Aspose.Words para .NET. Esta función le permite realizar un reemplazo de texto simple al buscar una cadena específica de caracteres y reemplazarla con otra cadena de caracteres en un documento de Word.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Creación de un nuevo documento

 Antes de que comencemos a usar la búsqueda y el reemplazo simples, necesitamos crear un nuevo documento usando Aspose.Words para .NET. Esto se puede hacer instanciando un`Document` objeto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Paso 2: Insertar texto en el documento

 Una vez que tenemos un documento, podemos insertar texto usando un`DocumentBuilder` objeto. En nuestro ejemplo, usamos el`Writeln` método para insertar la frase "Hola_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Paso 3: reemplazo de texto simple

 usamos el`Range.Replace` método para realizar el reemplazo de texto simple. En nuestro ejemplo, reemplazamos todas las apariciones de la cadena "_ClientName_ " con "James Bond" usando el`FindReplaceOptions` opción con el`FindReplaceDirection.Forward` dirección de búsqueda:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Paso 4: Guardar el documento editado

 Finalmente, guardamos el documento modificado en un directorio específico usando el`Save` método:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Código fuente de ejemplo para Simple Find Replace usando Aspose.Words para .NET

Aquí está el código fuente de ejemplo completo para demostrar el uso de la búsqueda simple y reemplazar con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Guardar el documento modificado
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Conclusión

En este artículo, exploramos el código fuente de C# para entender cómo usar la función de búsqueda simple y reemplazo de Aspose.Words para .NET. Seguimos una guía paso a paso para crear un documento, insertar texto, realizar un reemplazo de texto simple y guardar el documento editado.
