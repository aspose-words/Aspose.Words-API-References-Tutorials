---
title: Mover al campo de combinación
linktitle: Mover al campo de combinación
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a implementar la función Mover a campo de combinación en Aspose.Words para .NET con una guía paso a paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/move-to-merge-field/
---

En este ejemplo, exploraremos la característica Move To Merge Field de Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca de manipulación de documentos que permite a los desarrolladores crear, modificar y convertir documentos de Word mediante programación. La función Move To Merge Field nos permite navegar para combinar campos dentro de un documento y realizar varias operaciones en ellos.


## Explicando el código fuente paso a paso

Repasemos el código fuente paso a paso para entender cómo usar la función Mover a campo de combinación usando Aspose.Words para .NET.

## Paso 1: Inicializar el documento y el generador de documentos

Primero, inicialice los objetos Document y DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2 Insertar un campo de combinación y agregar texto después

Use el método InsertField de la clase DocumentBuilder para insertar un campo de combinación y luego agregue texto después de él:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Paso 3: el cursor del constructor se encuentra actualmente al final del documento.

```csharp
Assert.Null(builder.CurrentNode);
```
## Paso 4: mover el cursor del generador de documentos al campo de combinación

Para mover el cursor del generador de documentos al campo de combinación, utilice el método MoveToField de la clase DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## Agregar texto inmediatamente después del campo de combinación

Una vez que el cursor del generador de documentos se encuentre dentro del campo de combinación, puede agregar texto inmediatamente después de este mediante el método Escribir:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Código fuente de ejemplo para Mover a campo de combinación usando Aspose.Words para .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserte un campo usando DocumentBuilder y agregue una secuencia de texto después de él.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// El cursor del constructor se encuentra actualmente al final del documento.
Assert.Null(builder.CurrentNode);
// Podemos mover el constructor a un campo como este, colocando el cursor inmediatamente después del campo.
builder.MoveToField(field, true);

// Tenga en cuenta que el cursor está en un lugar más allá del nodo FieldEnd del campo, lo que significa que en realidad no estamos dentro del campo.
// Si deseamos mover el DocumentBuilder dentro de un campo,
// necesitaremos moverlo al nodo FieldStart o FieldSeparator de un campo usando el método DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Conclusión

hemos explorado la característica Move To Merge Field de Aspose.Words para .NET. Aprendimos a navegar para fusionar campos dentro de un documento usando la clase DocumentBuilder y realizar operaciones en ellos. Esta función es útil cuando se trabaja mediante programación con combinación

