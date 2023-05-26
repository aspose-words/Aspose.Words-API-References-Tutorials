---
title: Comparación de granularidad
linktitle: Comparación de granularidad
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda la característica Comparar granularidad de Aspose.Words para .NET que permite comparar documentos carácter por carácter e informar los cambios realizados.
type: docs
weight: 10
url: /es/net/compare-documents/comparison-granularity/
---
Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza la función Comparar granularidad de Aspose.Words para .NET.

## Paso 1: Introducción

La función Comparar granularidad de Aspose.Words para .NET le permite comparar documentos a nivel de carácter. Esto significa que cada carácter se comparará y los cambios se informarán en consecuencia.

## Paso 2: Configuración del entorno

Antes de comenzar, debe configurar su entorno de desarrollo para trabajar con Aspose.Words para .NET. Asegúrese de tener instalada la biblioteca Aspose.Words y tener un proyecto de C# adecuado para incrustar el código.

## Paso 3: agregue los ensamblajes necesarios

Para usar la función Comparar granularidad de Aspose.Words para .NET, debe agregar los ensamblajes necesarios a su proyecto. Asegúrese de tener las referencias adecuadas a Aspose.Words en su proyecto.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Paso 4: Creación de documentos

En este paso, crearemos dos documentos utilizando la clase DocumentBuilder. Estos documentos se utilizarán para la comparación.

```csharp
// Crear documento A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Crear documento B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Paso 5: Configuración de las opciones de comparación

En este paso, configuraremos las opciones de comparación para especificar la granularidad de comparación. Aquí usaremos granularidad a nivel de carácter.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Paso 6: Comparación de documentos

Ahora comparemos los documentos usando el método Compare de la clase Document. Los cambios se guardarán en el documento A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 El`Compare` El método compara el documento A con el documento B y guarda los cambios en el documento A. Puede especificar el nombre del autor y la fecha de comparación como referencia.

## Conclusión

En este artículo, exploramos la función Comparar granularidad de Aspose.Words para .NET. Esta característica le permite comparar documentos a nivel de carácter e informar cambios. Puede utilizar este conocimiento para realizar comparaciones detalladas de documentos en sus proyectos.

### Ejemplo de código fuente para la granularidad de comparación con Aspose.Words para .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```
