---
title: Objetivo de comparación
linktitle: Objetivo de comparación
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda la función de destino de comparación de Aspose.Words para .NET que le permite comparar documentos y generar un nuevo documento que contenga los cambios realizados.
type: docs
weight: 10
url: /es/net/compare-documents/comparison-target/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que usa la funcionalidad de destino de comparación de Aspose.Words para .NET.

## Paso 1: Introducción

La función de comparación de destino de Aspose.Words para .NET le permite comparar dos documentos y generar un nuevo documento que contenga los cambios realizados en el documento de destino. Esto puede ser útil para realizar un seguimiento de los cambios realizados entre diferentes versiones de un documento.

## Paso 2: Configuración del entorno

Antes de comenzar, debe configurar su entorno de desarrollo para trabajar con Aspose.Words para .NET. Asegúrese de tener instalada la biblioteca Aspose.Words y tener un proyecto de C# adecuado para incrustar el código.

## Paso 3: agregue los ensamblajes necesarios

Para utilizar la función de destino de comparación de Aspose.Words para .NET, debe agregar los ensamblados necesarios a su proyecto. Asegúrese de tener las referencias adecuadas a Aspose.Words en su proyecto.

```csharp
using Aspose.Words;
```

## Paso 4: Inicialización del documento

En este paso, inicializaremos dos documentos para comparar. Debe especificar la ruta del directorio donde se encuentran sus documentos, así como el nombre del documento de origen.

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Inicialización del documento A para comparar.
Document docA = new Document(dataDir + "DocumentA.docx");

// Clona el documento A para crear una copia idéntica del documento B.
Document docB = docA.Clone();
```

## Paso 5: Configuración de las opciones de comparación

En este paso, configuraremos las opciones de comparación para especificar el comportamiento de la comparación. Las opciones incluyen la capacidad de ignorar el formato, así como el objetivo de comparación, que es la opción "Mostrar cambios en" en el cuadro de diálogo "Comparar documentos" de Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Paso 6: Comparación de documentos

Ahora compararemos los documentos y generaremos el resultado en un nuevo documento.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 El`Compare` El método compara el documento A con el documento B y guarda los cambios en el documento A. Puede especificar el nombre de usuario y la fecha de comparación como referencia.

### Ejemplo de código fuente para el objetivo de comparación con Aspose.Words para .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Se relaciona con la opción "Mostrar cambios en" de Microsoft Word en el cuadro de diálogo "Comparar documentos".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Conclusión

En este artículo, exploramos la función de diff target de Aspose.Words para .NET. Esta función le permite comparar dos documentos y generar un nuevo documento que contenga los cambios realizados. Puede utilizar este conocimiento para realizar un seguimiento de los cambios entre diferentes versiones de sus documentos.

