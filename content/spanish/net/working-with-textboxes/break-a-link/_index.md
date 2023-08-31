---
title: Romper enlace hacia adelante en documento de Word
linktitle: Romper enlace hacia adelante en documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a romper vínculos hacia adelante en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET es una potente biblioteca que ofrece varias funciones para el procesamiento de textos con documentos de Microsoft Word mediante programación. Una de sus características útiles es la capacidad de romper enlaces hacia adelante en un documento de Word. En este tutorial, exploraremos el código fuente en C# que demuestra cómo dividir el enlace hacia adelante en un documento de Word usando Aspose.Words para .NET.

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

 Para romper un enlace hacia adelante en el cuadro de texto, podemos usar el`BreakForwardLink()` método. Este método rompe el enlace a la siguiente forma en la secuencia. El siguiente código muestra cómo romper un enlace directo:

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

## Conclusión

¡Felicidades! Ahora ha aprendido cómo romper enlaces de redirección en un documento de Word utilizando la biblioteca Aspose.Words para .NET. Siguiendo los pasos de esta guía, pudo configurar el documento, crear una forma de cuadro de texto y romper los enlaces de redireccionamiento utilizando diferentes métodos.

### Preguntas frecuentes sobre el enlace de avance en un documento de Word

#### P: ¿Cuál es la biblioteca que se usa para romper enlaces de redireccionamiento en un documento de Word usando Aspose.Words para .NET?

R: Para romper enlaces de redirección en un documento de Word usando Aspose.Words para .NET, la biblioteca utilizada es Aspose.Words para .NET.

#### P: ¿Cómo romper un enlace de redirección en un cuadro de texto?

 R: Para romper un enlace hacia adelante en un cuadro de texto, puede usar el`BreakForwardLink()` método. Este método rompe el enlace a la siguiente forma en la secuencia.

#### P: ¿Cómo romper un enlace de redirección estableciendo un valor nulo?

R: Alternativamente, puede romper un enlace de redirección configurando el`Next` propiedad del cuadro de texto para`null`. Esto elimina efectivamente la conexión con la siguiente forma.

#### P: ¿Cómo romper un enlace que conduce al cuadro de texto?

 R: En algunos casos, debe romper un enlace que conduce al cuadro de texto. Puede lograr esto llamando al`BreakForwardLink()` método en el`Previous` form, que rompe el enlace al TextBox.

#### P: ¿Podemos romper enlaces de redirección en elementos que no sean cuadros de texto?

R: Sí, con Aspose.Words para .NET es posible romper enlaces de redirección en diferentes elementos como párrafos, tablas, imágenes, etc. El proceso puede variar según el elemento específico en el que desee romper el enlace.