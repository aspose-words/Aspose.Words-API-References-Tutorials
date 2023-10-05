---
title: Reconocer y sustituciones dentro de patrones de reemplazo
linktitle: Reconocer y sustituciones dentro de patrones de reemplazo
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar patrones de reemplazo con reconocimientos y sustituciones en Aspose.Words para .NET para manipular documentos de Word.
type: docs
weight: 10
url: /es/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo utilizar la función Reconocer y sustituciones dentro de patrones de reemplazo en la biblioteca Aspose.Words para .NET. Esta característica ayuda a reconocer patrones de búsqueda complejos y realizar sustituciones basadas en grupos capturados durante la manipulación de documentos.

## Requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: crear un nuevo documento

Antes de comenzar a usar coincidencias y sustituciones en patrones de reemplazo, necesitamos crear un nuevo documento usando Aspose.Words para .NET. Esto se puede hacer creando una instancia de un`Document` objeto:

```csharp
Document doc = new Document();
```

## Paso 2: inserta texto en el documento

 Una vez que tenemos un documento, podemos insertar texto usando un`DocumentBuilder` objeto. En nuestro ejemplo, estamos usando el`Write` Método para insertar la frase "Jason le da algo de dinero a Paul". :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Paso 3: Reconocimientos y Sustituciones en Patrones de Reemplazo

 Ahora usaremos el`Range.Replace` función para realizar búsqueda y reemplazo de texto utilizando una expresión regular para reconocer patrones específicos. En nuestro ejemplo, usamos la expresión regular`([A-z]+) gives money to ([A-z]+)` Reconocer frases en las que alguien da dinero a otra persona. Usamos el patrón de reemplazo.`$2 takes money from $1` realizar la sustitución invirtiendo los roles. El uso de`$1` y`$2` se refiere a los grupos capturados por la expresión regular:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Código fuente de ejemplo para reconocimiento y sustituciones dentro de patrones de reemplazo usando Aspose.Words para .NET

Aquí está el código fuente de ejemplo completo para ilustrar el uso de coincidencias y sustituciones en patrones de reemplazo con Aspose.Words para .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo utilizar la función Reconocer y sustituciones dentro de patrones de reemplazo de Aspose.Words para .NET. Seguimos una guía paso a paso para crear un documento, insertar texto, realizar búsquedas y reemplazar usando expresiones regulares y patrones de sustitución basados en grupos capturados y manipular el documento.

### Preguntas frecuentes

#### P: ¿Qué es la función "Reconocimiento y sustituciones dentro de patrones de reemplazo" en Aspose.Words para .NET?

R: La función "Reconocer y sustituciones dentro de patrones de reemplazo" en Aspose.Words para .NET le permite reconocer patrones de búsqueda complejos usando expresiones regulares y realizar sustituciones basadas en los grupos capturados durante la manipulación de documentos. Le permite transformar dinámicamente el texto coincidente haciendo referencia a los grupos capturados en el patrón de reemplazo.

#### P: ¿Cómo puedo crear un documento nuevo usando Aspose.Words para .NET?

 R: Para crear un nuevo documento usando Aspose.Words para .NET, puede crear una instancia de un`Document` objeto. A continuación se muestra un ejemplo de código C# para crear un nuevo documento:

```csharp
Document doc = new Document();
```

#### P: ¿Cómo puedo insertar texto en un documento usando Aspose.Words para .NET?

 R: Una vez que tenga un documento, puede insertar texto usando un`DocumentBuilder` objeto. Por ejemplo, para insertar la frase "Jason le da dinero a Paul", puedes usar el`Write` método:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

#### P: ¿Cómo puedo realizar búsquedas y reemplazos de texto usando expresiones regulares en Aspose.Words para .NET?

 R: Para realizar búsqueda y reemplazo de texto usando expresiones regulares en Aspose.Words para .NET, puede usar el`Range.Replace` funcionar junto con un patrón de expresión regular. Puedes crear un`Regex` objeto con el patrón deseado y páselo al`Replace` método:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### P: ¿Cómo puedo utilizar grupos capturados en el patrón de reemplazo durante la búsqueda y reemplazo de texto en Aspose.Words para .NET?

 R: Para utilizar grupos capturados en el patrón de reemplazo durante la búsqueda y reemplazo de texto en Aspose.Words para .NET, puede habilitar la opción`UseSubstitutions` propiedad de la`FindReplaceOptions` objeto. Esto le permite hacer referencia a los grupos capturados utilizando`$1`, `$2`, etc. en el patrón de reemplazo:

```csharp
FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };
doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

#### P: ¿Qué demuestra el código fuente de ejemplo para la función "Reconocimiento y sustituciones dentro de patrones de reemplazo" en Aspose.Words para .NET?

R: El código fuente de ejemplo demuestra el uso de la función "Reconocer y sustituciones dentro de patrones de reemplazo" en Aspose.Words para .NET. Muestra cómo crear un documento, insertar texto, realizar búsqueda de texto y reemplazarlo usando expresiones regulares, y usar grupos capturados en el patrón de reemplazo para transformar dinámicamente el texto coincidente.

#### P: ¿Dónde puedo encontrar más información y ejemplos sobre el uso de expresiones regulares en Aspose.Words para .NET?

R: Para obtener más información y ejemplos sobre el uso de expresiones regulares en Aspose.Words para .NET, puede consultar el[Aspose.Words para referencias de API .NET](https://reference.aspose.com/words/net/). La documentación proporciona explicaciones detalladas y ejemplos de código para varios escenarios que involucran expresiones regulares y manipulación de texto en Aspose.Words para .NET.

#### P: ¿Puedo manipular otros aspectos del documento en función de los grupos capturados durante la búsqueda y reemplazo de texto?

R: Sí, puede manipular otros aspectos del documento según los grupos capturados durante la búsqueda y el reemplazo de texto. Además de realizar sustituciones de texto, puede modificar el formato, los estilos, la estructura del documento y otros elementos según los grupos capturados utilizando las diversas API proporcionadas por Aspose.Words para .NET.

#### P: ¿Existe alguna limitación o consideración al utilizar expresiones regulares y grupos capturados en Aspose.Words para .NET?

R: Si bien las expresiones regulares y los grupos capturados ofrecen poderosas capacidades para buscar y reemplazar texto en Aspose.Words para .NET, es importante considerar la complejidad y las implicaciones de rendimiento. Las expresiones regulares muy complejas y una gran cantidad de grupos capturados pueden afectar el rendimiento. Se recomienda probar y optimizar las expresiones regulares para sus casos de uso específicos para garantizar una manipulación eficiente de los documentos.

#### P: ¿Puedo utilizar la función "Reconocer y sustituciones dentro de patrones de reemplazo" con otros idiomas además del inglés?

R: Sí, la función "Reconocer y sustituciones dentro de patrones de reemplazo" en Aspose.Words para .NET se puede usar con otros idiomas además del inglés. Las expresiones regulares son independientes del idioma y se pueden diseñar para que coincidan con patrones específicos en cualquier idioma. Puede ajustar el patrón de expresión regular para adaptarlo al idioma que desee y a los patrones de texto específicos que desee reconocer y sustituir.