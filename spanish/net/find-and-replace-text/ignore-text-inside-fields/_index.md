---
title: Ignorar el texto dentro de los campos
linktitle: Ignorar el texto dentro de los campos
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar la función "Ignorar texto dentro de los campos" de Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/find-and-replace-text/ignore-text-inside-fields/
---
En este artículo, exploraremos el código fuente de C# anterior para comprender cómo usar la función Ignorar texto dentro de los campos en la biblioteca Aspose.Words para .NET. Esta característica es útil cuando queremos ignorar el texto dentro de los campos al manipular documentos.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Creación de un nuevo documento

 Antes de comenzar a manipular el texto dentro de los campos, debemos crear un nuevo documento usando Aspose.Words para .NET. Esto se puede hacer instanciando un`Document` objeto:

```csharp
Document doc = new Document();
```

## Paso 2: Insertar un campo con texto dentro

 Una vez que tenemos un documento, podemos insertar un campo que contenga texto dentro de él usando un`DocumentBuilder` objeto. Por ejemplo, para insertar un campo "INCLUDETEXT" con el texto "Text in field", podemos usar el`InsertField` método:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## Paso 3: Uso de la función Ignorar texto dentro de los campos

 Para ignorar el texto dentro de los campos en operaciones posteriores, podemos usar un`FindReplaceOptions` objeto y establecer el`IgnoreFields` propiedad a`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## Paso 4: Uso de expresiones regulares para buscar y reemplazar

Para realizar operaciones de búsqueda y reemplazo sobre el texto del documento, utilizaremos expresiones regulares. En nuestro ejemplo, buscaremos todas las ocurrencias de la letra "e" y las reemplazaremos con un asterisco "* ". Usaremos .NET's`Regex` clase para esto:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Paso 5: Ver la salida del documento modificado

Después de aplicar la búsqueda y reemplazo, podemos mostrar el contenido modificado del documento usando el`GetText` método:

```csharp
Console.WriteLine(doc.GetText());
```

## Paso 6: cambiar las opciones para incluir campos

 incluimos el texto dentro de los campos en el resultado de salida, podemos cambiar las opciones para no ignorar los campos. Para ello estableceremos el`IgnoreFields` propiedad a`false`:

```csharp
options.IgnoreFields = false;
```

## Paso 7: Mostrar el documento modificado con los campos

Después de cambiar las opciones, podemos realizar la búsqueda y reemplazar nuevamente para obtener el resultado con el texto dentro de los campos incluidos:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Código fuente de ejemplo para Ignorar campos internos de texto usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para demostrar el uso de la función Ignorar texto dentro de los campos con Aspose.Words para .NET:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Insertar campo con texto dentro.
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo usar la función Ignorar texto dentro de los campos en Aspose.Words para .NET. Seguimos una guía paso a paso para crear un documento, insertar un campo con texto dentro, usar la función Ignorar texto dentro de campos, realizar operaciones de búsqueda y reemplazo con expresiones regulares y mostrar el documento modificado.
