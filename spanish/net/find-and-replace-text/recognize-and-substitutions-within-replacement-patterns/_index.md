---
title: Reconocimiento y sustituciones dentro de patrones de reemplazo
linktitle: Reconocimiento y sustituciones dentro de patrones de reemplazo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar patrones de reemplazo con reconocimientos y sustituciones en Aspose.Words para .NET para manipular documentos de Word.
type: docs
weight: 10
url: /es/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo utilizar la función Reconocer y sustituciones dentro de patrones de reemplazo en la biblioteca Aspose.Words para .NET. Esta característica ayuda a reconocer patrones de búsqueda complejos y realizar sustituciones basadas en grupos capturados durante la manipulación de documentos.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Creación de un nuevo documento

 Antes de comenzar a usar coincidencias y sustituciones en patrones de reemplazo, debemos crear un nuevo documento usando Aspose.Words para .NET. Esto se puede hacer instanciando un`Document` objeto:

```csharp
Document doc = new Document();
```

## Paso 2: Insertar texto en el documento

 Una vez que tenemos un documento, podemos insertar texto usando un`DocumentBuilder`objeto. En nuestro ejemplo, estamos usando el`Write` método para insertar la frase "Jason le da a Paul algo de dinero". :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Paso 3: Reconocimientos y Sustituciones en Patrones de Reemplazo

 Ahora usaremos el`Range.Replace` función para realizar búsquedas de texto y reemplazar usando una expresión regular para reconocer patrones específicos. En nuestro ejemplo, usamos la expresión regular`([A-z]+) gives money to ([A-z]+)` reconocer oraciones donde alguien da dinero a otra persona. Usamos el patrón de reemplazo`$2 takes money from $1` realizar la sustitución invirtiendo los papeles. El uso de`$1` y`$2` se refiere a los grupos capturados por la expresión regular:

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

En este artículo, exploramos el código fuente de C# para entender cómo usar la función Reconocer y sustituir dentro de patrones de reemplazo de Aspose.Words para .NET. Seguimos una guía paso a paso para crear un documento, insertar texto, realizar búsquedas y reemplazos usando expresiones regulares y patrones de sustitución basados en grupos capturados y manipular el documento.
