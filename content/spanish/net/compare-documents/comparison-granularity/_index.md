---
title: Granularidad de comparación en documento de Word
linktitle: Granularidad de comparación en documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a comparar granularidad en la función de documentos de Word de Aspose.Words para .NET que permite comparar documentos carácter por carácter e informar los cambios realizados.
type: docs
weight: 10
url: /es/net/compare-documents/comparison-granularity/
---
Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función Comparar granularidad en documentos de Word de Aspose.Words para .NET.

## Paso 1: Introducción

La función Comparar granularidad de Aspose.Words para .NET le permite comparar documentos a nivel de caracteres. Esto significa que se comparará cada carácter y se informarán los cambios en consecuencia.

## Paso 2: configurar el entorno

Antes de comenzar, debe configurar su entorno de desarrollo para que funcione con Aspose.Words para .NET. Asegúrese de tener instalada la biblioteca Aspose.Words y tener un proyecto C# adecuado para incrustar el código.

## Paso 3: agregar los ensamblajes necesarios

Para utilizar la función Comparar granularidad de Aspose.Words para .NET, debe agregar los ensamblados necesarios a su proyecto. Asegúrese de tener las referencias adecuadas a Aspose.Words en su proyecto.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Paso 4: crear documentos

En este paso, crearemos dos documentos usando la clase DocumentBuilder. Estos documentos se utilizarán para la comparación.

```csharp
// Crear el documento A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Crear el documento B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Paso 5: configurar las opciones de comparación

En este paso, configuraremos las opciones de comparación para especificar la granularidad de la comparación. Aquí usaremos granularidad a nivel de personaje.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Paso 6: Comparación de documentos

Ahora comparemos los documentos usando el método Comparar de la clase Documento. Los cambios se guardarán en el documento A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 El`Compare`El método compara el documento A con el documento B y guarda los cambios en el documento A. Puede especificar el nombre del autor y la fecha de comparación como referencia.

## Conclusión

En este artículo, exploramos la función Comparar granularidad de Aspose.Words para .NET. Esta función le permite comparar documentos a nivel de carácter e informar cambios. Puede utilizar este conocimiento para realizar comparaciones detalladas de documentos en sus proyectos.

### Código fuente de muestra para granularidad de comparación usando Aspose.Words para .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## Conclusión

En este tutorial, exploramos la función Granularidad de comparación de Aspose.Words para .NET. Esta característica le permite especificar el nivel de detalle al comparar documentos. Al elegir diferentes niveles de granularidad, puede realizar comparaciones detalladas a nivel de carácter, palabra o bloque, según sus requisitos específicos. Aspose.Words para .NET proporciona una capacidad de comparación de documentos potente y flexible, lo que facilita la identificación de diferencias en documentos con distintos niveles de granularidad.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de utilizar la granularidad de comparación en Aspose.Words para .NET?

R: La granularidad de comparación en Aspose.Words para .NET le permite especificar el nivel de detalle al comparar documentos. Con esta función, puede comparar documentos en diferentes niveles, como a nivel de caracteres, a nivel de palabras o incluso a nivel de bloque. Cada nivel de granularidad proporciona un nivel diferente de detalle en los resultados de la comparación.

#### P: ¿Cómo uso la granularidad de comparación en Aspose.Words para .NET?

R: Para usar la granularidad de comparación en Aspose.Words para .NET, siga estos pasos:
1. Configure su entorno de desarrollo con la biblioteca Aspose.Words.
2. Agregue los ensamblajes necesarios a su proyecto haciendo referencia a Aspose.Words.
3.  Cree los documentos que desee comparar utilizando el`DocumentBuilder` clase.
4.  Configure las opciones de comparación creando un`CompareOptions` objeto y establecer el`Granularity` propiedad al nivel deseado (por ejemplo,`Granularity.CharLevel` para comparación a nivel de personaje).
5.  Utilizar el`Compare`método en un documento, pasando el otro documento y el`CompareOptions` objeto como parámetros. Este método comparará los documentos según la granularidad especificada y guardará los cambios en el primer documento.

#### P: ¿Cuáles son los niveles disponibles de granularidad de comparación en Aspose.Words para .NET?

R: Aspose.Words para .NET proporciona tres niveles de granularidad de comparación:
- `Granularity.CharLevel`: Compara documentos a nivel de carácter.
- `Granularity.WordLevel`: Compara documentos a nivel de palabra.
- `Granularity.BlockLevel`: Compara documentos a nivel de bloque.

#### P: ¿Cómo puedo interpretar los resultados de la comparación con granularidad a nivel de carácter?

R: Con granularidad a nivel de carácter, cada carácter en los documentos comparados se analiza en busca de diferencias. Los resultados de la comparación mostrarán cambios a nivel de personaje individual, incluidas adiciones, eliminaciones y modificaciones.