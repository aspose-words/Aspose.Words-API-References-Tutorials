---
title: Romper enlace directo en documento de Word
linktitle: Romper enlace directo en documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a romper enlaces directos en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-textboxes/break-a-link/
---

Aspose.Words para .NET es una potente biblioteca que ofrece varias funciones para el procesamiento de textos con documentos de Microsoft Word mediante programación. Una de sus características útiles es la capacidad de dividir enlaces directos en un documento de Word. En este tutorial, exploraremos el código fuente en C# que demuestra cómo romper un enlace directo en un documento de Word usando Aspose.Words para .NET.

## Paso 1: Vista previa del código fuente de C#

El código fuente de C# proporcionado se centra en la función "Romper un vínculo" de Aspose.Words para .NET. Muestra cómo romper un enlace en forma de cuadro de texto dentro de un documento. El código presenta diferentes escenarios para romper enlaces y proporciona instrucciones claras sobre cómo lograr los resultados deseados.

## Paso 2: configurar el documento y crear una forma de cuadro de texto

 Para comenzar, necesitamos configurar el documento y crear una forma de cuadro de texto. El siguiente código inicializa una nueva instancia del`Document` clase y crea una forma de cuadro de texto:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Paso 3: romper el enlace de avance en TextBox

 Para romper un enlace de reenvío en el TextBox, podemos usar el`BreakForwardLink()` método. Este método rompe el vínculo con la siguiente forma de la secuencia. El siguiente código muestra cómo romper un enlace directo:

```csharp
textBox.BreakForwardLink();
```

## Paso 4: rompa un enlace directo estableciendo un valor nulo

 Alternativamente, podemos romper un enlace directo configurando el TextBox`Next`propiedad a`null`. Esto elimina efectivamente la conexión con la siguiente forma. El siguiente código demuestra este enfoque:

```csharp
textBox. Next = null;
```

## Paso 5: rompa un enlace que conduce al cuadro de texto

 En algunos casos, necesitamos romper un vínculo que conduce a la forma del cuadro de texto. Podemos lograr esto llamando al`BreakForwardLink()` método en el`Previous` formulario, que rompe el enlace al TextBox. A continuación se muestra un ejemplo de cómo romper dicho vínculo:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Código fuente de muestra para romper un enlace con Aspose.Words para .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Romper el enlace directo.
textBox.BreakForwardLink();

// Rompe un enlace directo estableciendo un valor nulo.
textBox. Next = null;

// Rompe un enlace que conduce a este cuadro de texto.
textBox.Previous?.BreakForwardLink();
```

## Conclusión

¡Enhorabuena! Ahora ha aprendido cómo romper enlaces de redireccionamiento en un documento de Word usando la biblioteca Aspose.Words para .NET. Siguiendo los pasos de esta guía, pudo configurar el documento, crear una forma de cuadro de texto y romper los enlaces de redireccionamiento utilizando diferentes métodos.

### Preguntas frecuentes sobre cómo romper el enlace hacia adelante en un documento de Word

#### P: ¿Cuál es la biblioteca que se utiliza para romper enlaces de redireccionamiento en un documento de Word usando Aspose.Words para .NET?

R: Para romper enlaces de redireccionamiento en un documento de Word usando Aspose.Words para .NET, la biblioteca utilizada es Aspose.Words para .NET.

#### P: ¿Cómo romper un enlace de redireccionamiento en un TextBox?

 R: Para romper un vínculo de reenvío en un cuadro de texto, puede utilizar el`BreakForwardLink()` método. Este método rompe el vínculo con la siguiente forma de la secuencia.

#### P: ¿Cómo romper un enlace de redireccionamiento estableciendo un valor nulo?

R: Alternativamente, puedes romper un enlace de redireccionamiento configurando el`Next` propiedad del TextBox para`null`. Esto elimina efectivamente la conexión con la siguiente forma.

#### P: ¿Cómo romper un enlace que conduce al TextBox?

 R: En algunos casos es necesario romper un vínculo que conduce al cuadro de texto. Puedes lograr esto llamando al`BreakForwardLink()` método en el`Previous` formulario, que rompe el enlace al TextBox.

#### P: ¿Podemos romper enlaces de redireccionamiento en elementos que no sean cuadros de texto?

R: Sí, con Aspose.Words para .NET es posible romper enlaces de redireccionamiento en diferentes elementos como párrafos, tablas, imágenes, etc. El proceso puede variar según el elemento específico en el que desea romper el enlace.