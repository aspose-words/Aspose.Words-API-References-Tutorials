---
title: Reemplazar con cadena
linktitle: Reemplazar con cadena
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a reemplazar texto con una cadena en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/find-and-replace-text/replace-with-string/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función Reemplazar con cadena en la biblioteca Aspose.Words para .NET. Esta función le permite realizar el reemplazo de texto en función de una cadena de caracteres específica en un documento de Word.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Creación de un nuevo documento

Antes de comenzar a usar el reemplazo de cadenas, debemos crear un nuevo documento usando Aspose.Words para .NET. Esto se puede hacer instanciando un`Document` objeto:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Paso 2: Insertar texto en el documento

 Una vez que tenemos un documento, podemos insertar texto usando un`DocumentBuilder` objeto. En nuestro ejemplo, usamos el`Writeln` método para insertar la frase "sad crazy bad":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Paso 3: Reemplazar con una cadena

 usamos el`Range.Replace` método para reemplazar texto con una cadena. En nuestro ejemplo, reemplazamos todas las ocurrencias de la palabra "triste" con "malo" usando el`FindReplaceOptions` opción con el`FindReplaceDirection.Forward` dirección de búsqueda:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Paso 4: Guardar el documento editado

 Finalmente, guardamos el documento modificado en un directorio específico usando el`Save` método:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Código fuente de ejemplo para Reemplazar con cadena usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para ilustrar el uso de reemplazar con una cadena de caracteres con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Conclusión

En este artículo, exploramos el código fuente de C# para entender cómo usar la función Reemplazar con cadena de Aspose.Words para .NET. Seguimos una guía paso a paso para crear un documento, insertar texto, reemplazar con una cadena y guardar el documento modificado.
