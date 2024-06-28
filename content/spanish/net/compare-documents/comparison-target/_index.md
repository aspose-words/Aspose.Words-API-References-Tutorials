---
title: Objetivo de comparación en documento de Word
linktitle: Objetivo de comparación en documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a comparar objetivos en la función de documentos de Word de Aspose.Words para .NET que le permite comparar documentos y generar un nuevo documento que contenga los cambios realizados.
type: docs
weight: 10
url: /es/net/compare-documents/comparison-target/
---
Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que utiliza el destino de comparación en la funcionalidad de documentos de Word de Aspose.Words para .NET.

## Paso 1: Introducción

La función de comparación de destino de Aspose.Words para .NET le permite comparar dos documentos y generar un nuevo documento que contiene los cambios realizados en el documento de destino. Esto puede resultar útil para realizar un seguimiento de los cambios realizados entre diferentes versiones de un documento.

## Paso 2: configurar el entorno

Antes de comenzar, debe configurar su entorno de desarrollo para que funcione con Aspose.Words para .NET. Asegúrese de tener instalada la biblioteca Aspose.Words y tener un proyecto C# adecuado para incrustar el código.

## Paso 3: agregar los ensamblajes necesarios

Para utilizar la función de destino de comparación de Aspose.Words para .NET, debe agregar los ensamblados necesarios a su proyecto. Asegúrese de tener las referencias adecuadas a Aspose.Words en su proyecto.

```csharp
using Aspose.Words;
```

## Paso 4: Inicialización del documento

En este paso, inicializaremos dos documentos para compararlos. Debe especificar la ruta del directorio donde se encuentran sus documentos, así como el nombre del documento fuente.

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Inicialización del documento A para comparar.
Document docA = new Document(dataDir + "DocumentA.docx");

// Clone el documento A para crear una copia idéntica del documento B.
Document docB = docA.Clone();
```

## Paso 5: configurar las opciones de comparación

En este paso, configuraremos las opciones de comparación para especificar el comportamiento de la comparación. Las opciones incluyen la capacidad de ignorar el formato, así como el objetivo de comparación, que es la opción "Mostrar cambios en" en el cuadro de diálogo "Comparar documentos" de Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Paso 6: Comparación de documentos

Ahora compararemos los documentos y generaremos el resultado en un nuevo documento.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 El`Compare`El método compara el documento A con el documento B y guarda los cambios en el documento A. Puede especificar el nombre de usuario y la fecha de comparación como referencia.

### Código fuente de muestra para Compare Target usando Aspose.Words para .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Se relaciona con la opción "Mostrar cambios en" de Microsoft Word en el cuadro de diálogo "Comparar documentos".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Conclusión

En este artículo, exploramos la función de destino de diferenciación de Aspose.Words para .NET. Esta función le permite comparar dos documentos y generar un nuevo documento que contenga los cambios realizados. Puede utilizar este conocimiento para realizar un seguimiento de los cambios entre diferentes versiones de sus documentos.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de utilizar Comparison Target en Aspose.Words para .NET?

R: Comparación de destino en Aspose.Words para .NET le permite comparar dos documentos y generar un nuevo documento que contiene los cambios realizados en el documento de destino. Esta función es útil para realizar un seguimiento de los cambios realizados entre diferentes versiones de un documento y visualizar las diferencias en un documento separado.

#### P: ¿Cómo uso Comparation Target en Aspose.Words para .NET?

R: Para usar Comparison Target en Aspose.Words para .NET, siga estos pasos:
1. Configure su entorno de desarrollo con la biblioteca Aspose.Words.
2. Agregue los ensamblajes necesarios a su proyecto haciendo referencia a Aspose.Words.
3.  Inicialice los documentos que desea comparar utilizando el`Document` clase o el`DocumentBuilder` clase.
4.  Configure las opciones de comparación creando un`CompareOptions` objetos y propiedades de configuración como`IgnoreFormatting` y`Target` (p.ej.,`ComparisonTargetType.New` para objetivo de comparación).
5.  Utilizar el`Compare` método en un documento, pasando el otro documento y el`CompareOptions` objeto como parámetros. Este método comparará los documentos y guardará los cambios en el primer documento.

####  P: ¿Cuál es el propósito de la`Target` property in the `CompareOptions` class?

 R: El`Target` propiedad en el`CompareOptions` La clase le permite especificar el destino de la comparación, que es similar a la opción "Mostrar cambios en" en el cuadro de diálogo "Comparar documentos" de Microsoft Word. El objetivo se puede establecer en`ComparisonTargetType.New` para mostrar cambios en un nuevo documento,`ComparisonTargetType.Current` para mostrar cambios en el documento actual, o`ComparisonTargetType.Formatting` para mostrar solo los cambios de formato.