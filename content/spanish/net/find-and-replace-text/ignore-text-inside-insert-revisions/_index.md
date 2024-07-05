---
title: Ignorar texto dentro de revisiones de inserción
linktitle: Ignorar texto dentro de revisiones de inserción
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar la función "Ignorar texto dentro de revisiones de inserción" de Aspose.Words para .NET para manipular revisiones de inserción en documentos de Word.
type: docs
weight: 10
url: /es/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo utilizar la función Ignorar texto dentro de insertar revisiones en la biblioteca Aspose.Words para .NET. Esta característica es útil cuando queremos ignorar el texto dentro de las revisiones de inserción mientras manipulamos documentos.

## Requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: crear un nuevo documento

 Antes de comenzar a manipular texto dentro de las revisiones de inserción, necesitamos crear un nuevo documento usando Aspose.Words para .NET. Esto se puede hacer creando una instancia de un`Document` objeto:

```csharp
Document doc = new Document();
```

## Paso 2: Insertar texto con seguimiento de revisiones

 Una vez que tenemos un documento, podemos insertar texto con seguimiento de revisión usando un`DocumentBuilder`objeto. Por ejemplo, para insertar el texto "Insertado" con seguimiento de revisión, podemos usar el`StartTrackRevisions`, `Writeln` y`StopTrackRevisions` métodos:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Paso 3: inserta texto no revisado

 Además del texto con seguimiento de revisión, también podemos insertar texto no revisado usando el`DocumentBuilder` objeto. Por ejemplo, para insertar el texto "Texto" sin revisión, podemos utilizar el`Write` método:

```csharp
builder.Write("Text");
```

## Paso 4: uso de la función Ignorar texto dentro de Insertar revisiones

 Para ignorar el texto dentro de las revisiones de inserción en operaciones posteriores, podemos usar un`FindReplaceOptions` objeto y establecer el`IgnoreInserted`propiedad a`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Paso 5: usar expresiones regulares para buscar y reemplazar

Para realizar operaciones de búsqueda y reemplazo en el texto del documento, usaremos expresiones regulares. En nuestro ejemplo, buscaremos todas las apariciones de la letra "e" y las reemplazaremos con un asterisco ".* ". Usaremos .NET`Regex` clase para esto:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Paso 6: Ver el resultado del documento modificado

 Después de aplicar la búsqueda y reemplazo, podemos mostrar el contenido modificado del documento usando el`GetText` método:

```csharp
Console.WriteLine(doc.GetText());
```

## Paso 7: cambiar las opciones para incluir revisiones de inserción

Si queremos incluir el texto dentro de las revisiones de inserción en el resultado de salida, podemos cambiar las opciones para no ignorar las revisiones de inserción. Para ello estableceremos el`IgnoreInserted`propiedad a`false`:

```csharp
options.IgnoreInserted = false;
```

## Paso 8: Ver el documento modificado con revisiones de inserción

Después de cambiar las opciones, podemos realizar la búsqueda y reemplazar nuevamente para obtener el resultado con el texto dentro de las revisiones de inserción incluidas:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Código fuente de ejemplo para ignorar texto dentro de revisiones de inserción usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para demostrar el uso de la función Ignorar texto dentro de Insertar revisiones con Aspose.Words para .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Insertar texto con revisiones de seguimiento.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Insertar texto no revisado.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo utilizar la función Ignorar texto dentro de Insertar revisiones en Aspose.Words para .NET. Seguimos una guía paso a paso para crear un documento, insertar texto con revisiones de seguimiento y texto no revisado, usar la función Ignorar texto dentro de insertar revisiones, realizar operaciones de búsqueda y reemplazo con expresiones regulares y mostrar el documento modificado.

### Preguntas frecuentes

#### P: ¿Qué es la función "Ignorar texto dentro de revisiones de inserción" en Aspose.Words para .NET?

R: La función "Ignorar texto dentro de las revisiones de inserción" en Aspose.Words para .NET le permite especificar si el texto dentro de las revisiones de inserción debe ignorarse durante ciertas operaciones, como buscar y reemplazar texto. Cuando esta característica está habilitada, el texto dentro de las revisiones de inserción no se considera durante las operaciones.

#### P: ¿Cómo puedo crear un documento nuevo usando Aspose.Words para .NET?

 R: Para crear un nuevo documento usando Aspose.Words para .NET, puede crear una instancia de un`Document` objeto. A continuación se muestra un ejemplo de código C# para crear un nuevo documento:

```csharp
Document doc = new Document();
```

#### P: ¿Cómo puedo insertar texto con seguimiento de revisión en Aspose.Words para .NET?

R: Una vez que tenga un documento, puede insertar texto con seguimiento de revisión usando un`DocumentBuilder` objeto. Por ejemplo, para insertar el texto "Insertado" con seguimiento de revisión, puede utilizar el`StartTrackRevisions`, `Writeln` , y`StopTrackRevisions` métodos:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### P: ¿Cómo puedo insertar texto no revisado en Aspose.Words para .NET?

 R: Además del texto con seguimiento de revisión, también puede insertar texto no revisado utilizando el`DocumentBuilder` objeto. Por ejemplo, para insertar el texto "Texto" sin revisión, puede utilizar el`Write` método:

```csharp
builder.Write("Text");
```

#### P: ¿Cómo puedo ignorar el texto dentro de las revisiones de inserción en Aspose.Words para .NET?

 R: Para ignorar el texto dentro de las revisiones de inserción durante operaciones posteriores, puede utilizar un`FindReplaceOptions` objeto y establecer el`IgnoreInserted`propiedad a`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### P: ¿Cómo puedo realizar búsquedas y reemplazos usando expresiones regulares en Aspose.Words para .NET?

 R: Para realizar operaciones de búsqueda y reemplazo en el texto del documento usando expresiones regulares, puede usar .NET`Regex` clase. Por ejemplo, para buscar todas las apariciones de la letra "e" y reemplazarlas con un asterisco "* ", puedes crear un`Regex` objeto y utilizarlo con el`Replace` método:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### P: ¿Cómo puedo ver el resultado modificado del documento en Aspose.Words para .NET?

 R: Después de aplicar las operaciones de búsqueda y reemplazo, puede ver el contenido modificado del documento usando el`GetText` método:

```csharp
Console.WriteLine(doc.GetText());
```

#### P: ¿Cómo puedo incluir las revisiones de inserción en el resultado de salida en Aspose.Words para .NET?

 R: Para incluir el texto dentro de las revisiones de inserción en el resultado de salida, puede cambiar las opciones para no ignorar las revisiones de inserción. Para esto, puede configurar el`IgnoreInserted` propiedad de la`FindReplaceOptions` oponerse a`false`:

```csharp
options.IgnoreInserted = false;
```

#### P: ¿Cómo puedo mostrar el documento modificado con las revisiones insertadas en Aspose.Words para .NET?

R: Después de cambiar las opciones para incluir revisiones de inserción, puede realizar la búsqueda y reemplazar nuevamente para obtener el resultado con el texto dentro de las revisiones de inserción incluidas:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```