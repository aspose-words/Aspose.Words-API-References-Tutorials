---
title: Mover al párrafo
linktitle: Mover al párrafo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar Aspose.Words para la función Mover a párrafo de .NET para navegar y manipular párrafos en documentos de Word mediante programación.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/move-to-paragraph/
---

En este ejemplo paso a paso, exploraremos la función Mover a párrafo de Aspose.Words para .NET. Esta función permite a los desarrolladores navegar y manipular párrafos dentro de un documento de Word mediante programación. Al seguir esta guía, aprenderá cómo implementar y utilizar la función Mover a párrafo de manera efectiva.

El código anterior demuestra el uso de la función Mover a párrafo. Entendamos cada paso en detalle:

## Paso 1: Cargar el documento

 Comenzamos cargando el documento de Word en una instancia del`Document` clase. El`MyDir`variable representa la ruta del directorio donde se encuentra el documento. Debe reemplazarlo con la ruta del directorio real o modificar el código en consecuencia.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
```

## Paso 2: inicialización de DocumentBuilder

 A continuación, creamos un`DocumentBuilder` objeto y asociarlo con el documento cargado. El`DocumentBuilder` La clase proporciona varios métodos y propiedades para manipular el contenido del documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: pasar a un párrafo específico

 El`MoveToParagraph` se utiliza para colocar el generador de documentos en un párrafo específico dentro del documento. Toma dos parámetros: el índice del párrafo de destino y la posición del carácter dentro de ese párrafo (0 representa el comienzo del párrafo).

En el ejemplo proporcionado, vamos al tercer párrafo (índice 2) del documento:

```csharp
builder.MoveToParagraph(2, 0);
```

## Paso 4: Modificar el contenido del párrafo

 Una vez que el constructor está posicionado en el párrafo deseado, podemos usar el`Writeln`para agregar o modificar el contenido de ese párrafo. En este caso, estamos agregando el texto "Este es el tercer párrafo".

```csharp
builder.Writeln("This is the 3rd paragraph.");
```

### Código fuente de ejemplo para Mover a párrafo usando Aspose.Words para .NET

A continuación se muestra el código fuente de ejemplo completo para implementar la función Mover a párrafo utilizando Aspose.Words para .NET:

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.MoveToParagraph(2, 0);
builder.Writeln("This is the 3rd paragraph.");
```

Al seguir esta guía y utilizar la función Mover a párrafo, puede manipular párrafos dentro de documentos de Word mediante programación usando Aspose.Words para .NET.

