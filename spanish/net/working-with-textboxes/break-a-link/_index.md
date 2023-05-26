---
title: romper un enlace
linktitle: romper un enlace
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a romper vínculos en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET es una poderosa biblioteca que ofrece varias funciones para trabajar con documentos de Microsoft Word mediante programación. Una de sus características útiles es la capacidad de romper enlaces dentro de un documento. En este tutorial, exploraremos el código fuente en C# que demuestra cómo romper un enlace usando Aspose.Words para .NET.

## Paso 1: Vista previa del código fuente de C#

El código fuente de C# proporcionado se centra en la función "Romper un enlace" de Aspose.Words para .NET. Muestra cómo romper un enlace en una forma de cuadro de texto dentro de un documento. El código presenta diferentes escenarios para romper enlaces y proporciona instrucciones claras sobre cómo lograr los resultados deseados.

## Paso 2: configurar el documento y crear una forma de cuadro de texto

 Para comenzar, debemos configurar el documento y crear una forma de cuadro de texto. El siguiente código inicializa una nueva instancia del`Document` clase y crea una forma de cuadro de texto:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Paso 3: Rompe el enlace hacia adelante en TextBox

 Para romper un enlace hacia adelante en el cuadro de texto, podemos usar el`BreakForwardLink()`método. Este método rompe el enlace a la siguiente forma en la secuencia. El siguiente código muestra cómo romper un enlace directo:

```csharp
textBox.BreakForwardLink();
```

## Paso 4: rompa un enlace directo estableciendo un valor nulo

 Alternativamente, podemos romper un enlace hacia adelante configurando el TextBox`Next` propiedad a`null`. Esto elimina efectivamente la conexión con la siguiente forma. El siguiente código demuestra este enfoque:

```csharp
textBox. Next = null;
```

## Paso 5: rompa un enlace que lleva al cuadro de texto

 En algunos casos, necesitamos romper un vínculo que conduce a la forma de cuadro de texto. Podemos lograr esto llamando al`BreakForwardLink()` método en el`Previous` form, que rompe el enlace al TextBox. Aquí hay un ejemplo de cómo romper dicho enlace:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Ejemplo de código fuente para romper un vínculo con Aspose.Words para .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Romper el enlace directo.
textBox.BreakForwardLink();

// Rompe un enlace directo estableciendo un valor nulo.
textBox. Next = null;

// Rompe un enlace que lleva a este cuadro de texto.
textBox.Previous?.BreakForwardLink();
```

