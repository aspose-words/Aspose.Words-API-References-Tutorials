---
title: Reemplazar con expresiones regulares
linktitle: Reemplazar con expresiones regulares
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a realizar el reemplazo de texto basado en expresiones regulares en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/find-and-replace-text/replace-with-regex/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función Reemplazar con Regex en la biblioteca Aspose.Words para .NET. Esta característica le permite realizar reemplazos de texto basados en patrones específicos definidos por una expresión regular.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Creación de un nuevo documento

 Antes de comenzar a usar el reemplazo de expresiones regulares, debemos crear un nuevo documento usando Aspose.Words para .NET. Esto se puede hacer instanciando un`Document` objeto:

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

## Paso 3: Configurar las opciones de Buscar y reemplazar

 Ahora configuraremos las opciones de buscar y reemplazar usando un`FindReplaceOptions` objeto. En nuestro ejemplo, usamos las opciones predeterminadas:

```csharp
FindReplaceOptions options = new FindReplaceOptions();
```

## Paso 4: Reemplazar con una expresión regular

 usamos el`Range.Replace` método para realizar el reemplazo de texto usando una expresión regular. En nuestro ejemplo, usamos la expresión regular "[s|m]ad" to find the words "sad" and "mad" and replace them with the word "bad":

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

## Paso 5: Guardar el documento modificado

 Finalmente, guardamos el documento modificado en un directorio específico usando el`Save` método:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
```

### Ejemplo de código fuente para Reemplazar con Regex usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para demostrar el uso del reemplazo de expresiones regulares con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	FindReplaceOptions options = new FindReplaceOptions();

	doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
  
```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo usar la función Reemplazar con Regex de Aspose.Words para .NET. Seguimos una guía paso a paso para crear un documento, insertar texto, realizar el reemplazo con una expresión regular y guardar el documento modificado.
