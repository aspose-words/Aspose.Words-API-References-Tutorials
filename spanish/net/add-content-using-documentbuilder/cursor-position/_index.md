---
title: Posición del cursor
linktitle: Posición del cursor
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda cómo recuperar la posición del cursor en un documento de Word usando Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/cursor-position/
---

En este ejemplo paso a paso, aprenderá sobre la posición del cursor en un documento de Word utilizando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá recuperar el nodo y el párrafo actual donde se encuentra el cursor en el documento.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: acceda al nodo y párrafo actual
A continuación, recupere el nodo actual y el párrafo donde se encuentra el cursor. Esto se puede lograr utilizando las propiedades CurrentNode y CurrentParagraph de la clase DocumentBuilder:

```csharp
Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;
```

## Paso 3: Recuperar la información de la posición del cursor
Ahora, puede recuperar información sobre la posición del cursor. En el siguiente fragmento de código, imprimimos el texto del párrafo actual:

```csharp
Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

### Ejemplo de código fuente para la posición del cursor usando Aspose.Words para .NET
Aquí está el código fuente completo para comprender la posición del cursor usando Aspose.Words para .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Node curNode = builder.CurrentNode;
Paragraph curParagraph = builder.CurrentParagraph;

Console.WriteLine("\nCursor move to paragraph: " + curParagraph.GetText());
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo trabajar con la posición del cursor en un documento de Word utilizando Aspose.Words para .NET. Al seguir la guía paso a paso y utilizar el código fuente proporcionado, ahora puede recuperar el nodo y el párrafo actual donde se encuentra el cursor en el documento.

Comprender la posición del cursor es útil para varios escenarios, como la manipulación del contenido del documento en función de la ubicación del cursor o la implementación de funciones de edición personalizadas.

