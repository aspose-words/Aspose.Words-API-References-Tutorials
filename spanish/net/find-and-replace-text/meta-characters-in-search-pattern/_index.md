---
title: Metacaracteres en el patrón de búsqueda
linktitle: Metacaracteres en el patrón de búsqueda
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar metacaracteres en el patrón de búsqueda con Aspose.Words para .NET para manipular documentos de Word.
type: docs
weight: 10
url: /es/net/find-and-replace-text/meta-characters-in-search-pattern/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo usar la función Metacaracteres en el patrón de búsqueda en la biblioteca Aspose.Words para .NET. Esta característica le permite usar metacaracteres especiales para realizar búsquedas avanzadas y reemplazos en documentos de Word.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Creación de un nuevo documento

 Antes de comenzar a usar metacaracteres en el patrón de búsqueda, debemos crear un nuevo documento usando Aspose.Words para .NET. Esto se puede hacer instanciando un`Document` objeto:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Paso 2: Insertar texto en el documento

 Una vez que tenemos un documento, podemos insertar texto usando un`DocumentBuilder` objeto. En nuestro ejemplo, usamos el`Writeln` y`Write` métodos para insertar dos líneas de texto:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Paso 3: busque y reemplace texto con metacaracteres

 Ahora usaremos el`Range.Replace` función para buscar y reemplazar texto utilizando un patrón de búsqueda que contiene metacaracteres especiales. En nuestro ejemplo, reemplazamos la frase "Esta es la línea 1&pEsta es la línea 2" con "Esta línea se reemplaza" usando el`&p` metacarácter para representar un salto de párrafo:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Paso 4: Insertar un salto de página en el documento

 Para ilustrar el uso de otro metacarácter, insertaremos un salto de página en el documento usando el`InsertBreak` método con el`BreakType.PageBreak` parámetro. Primero movemos el cursor de la`DocumentBuilder` hasta el final del documento, luego insertamos el salto de página y una nueva línea de texto:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Paso 5: busque y reemplace con otro metacarácter

 Ahora realizaremos otra búsqueda y reemplazo usando el`&m` metacarácter para representar un salto de página. Reemplazamos la frase "Esta es la línea 1&mEsta es la línea 2" por "El salto de página se reemplaza con texto nuevo". :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Paso 6: Guardar el documento editado

 Finalmente, guardamos el documento modificado en un directorio específico usando el`Save` método:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Ejemplo de código fuente para metacaracteres en el patrón de búsqueda usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para demostrar el uso de metacaracteres en el patrón de búsqueda con Aspose.Words para .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo usar los metacaracteres en el patrón de búsqueda de Aspose.Words para .NET. Seguimos una guía paso a paso para crear un documento, insertar texto, realizar búsquedas y reemplazar usando metacaracteres especiales, insertar saltos de página y guardar el documento editado.
