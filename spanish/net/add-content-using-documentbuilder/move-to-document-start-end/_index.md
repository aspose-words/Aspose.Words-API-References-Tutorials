---
title: Mover a Documento Inicio Fin
linktitle: Mover a Documento Inicio Fin
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a usar Aspose.Words para .NET para pasar al principio y al final del documento en documentos de Word con esta guía paso a paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/move-to-document-start-end/
---

En este ejemplo, exploraremos la función Mover al inicio/fin del documento de Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca de manipulación de documentos que permite a los desarrolladores crear, modificar y convertir documentos de Word mediante programación. La característica Move To Document Start/End nos permite navegar hasta el principio o el final de un documento utilizando la clase DocumentBuilder.

## Explicando el código fuente paso a paso

Repasemos el código fuente paso a paso para entender cómo usar la función Mover al inicio/fin del documento usando Aspose.Words para .NET.


## Paso 1: Inicializar el documento y el generador de documentos

A continuación, inicialice los objetos Document y DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Ir al inicio del documento

Para mover la posición del cursor al principio del documento, utilice el método MoveToDocumentStart de la clase DocumentBuilder:

```csharp
builder.MoveToDocumentStart();
```

## Paso 3: Ir al final del documento

Para mover la posición del cursor al final del documento, utilice el método MoveToDocumentEnd de la clase DocumentBuilder:

```csharp
builder.MoveToDocumentEnd();
```

## Paso 4: Salida de la posición del cursor

Puede generar la posición del cursor usando Console.WriteLine o cualquier otro método deseado. Por ejemplo:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### Ejemplo de código fuente para Mover al inicio/fin del documento usando Aspose.Words para .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Mueva la posición del cursor al principio de su documento.
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

// Mueva la posición del cursor al final de su documento.
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## Conclusión

En este ejemplo, hemos explorado la función Mover al inicio/fin del documento de Aspose.Words para .NET. Aprendimos a navegar hasta el principio y el final de un documento usando la clase DocumentBuilder. Esta función es útil cuando se procesan textos mediante programación con documentos de Word y es necesario manipular o insertar contenido en posiciones específicas dentro del documento.