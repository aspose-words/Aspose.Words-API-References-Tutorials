---
title: Código en línea
linktitle: Código en línea
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar código con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/inline-code/
---

En este ejemplo, le explicaremos cómo utilizar la función de código en línea con Aspose.Words para .NET. El código en línea se utiliza para representar visualmente fragmentos de código dentro de un párrafo.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: agregue estilo para el código en línea

 Agregaremos un estilo personalizado para el código en línea usando el`Styles.Add` método de la`Document` objeto. En este ejemplo, estamos creando un estilo llamado "InlineCode" para código en línea con una comilla invertida predeterminada.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Paso 3: agregar código en línea

Ahora podemos agregar código en línea usando el estilo personalizado "InlineCode". En este ejemplo, agregamos dos fragmentos de texto con diferentes números de acentos graves.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Código fuente de ejemplo para código en línea con Aspose.Words para .NET

```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// Se omite el número de acentos graves; se utilizará un acento grave de forma predeterminada.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Habrá 3 comillas invertidas.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

¡Enhorabuena! Ahora ha aprendido a utilizar la funcionalidad de código en línea con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo puedo utilizar el código en línea en Aspose.Words?

R: Para usar código en línea en Aspose.Words, puede usar etiquetas apropiadas para rodear el texto que se va a formatear como código en línea. Por ejemplo, puedes utilizar el`<code>` o`<kbd>` etiqueta para rodear el texto que se formateará como código en línea.

#### P: ¿Es posible especificar la fuente o el color del código en línea en Aspose.Words?

 R: Sí, puede especificar la fuente o el color del código en línea en Aspose.Words. Puedes usar el`Font.Name`y`Font.Color` propiedades de la`Run` objeto para establecer la fuente y el color del código en línea. Por ejemplo, puedes usar`run.Font.Name = "Courier New"` para especificar la fuente para el código en línea y`run.Font.Color = Color.Blue` para especificar el color.

#### P: ¿Puedo usar el código en línea en un párrafo que contenga otros elementos de texto?

 R: Sí, puedes usar el código en línea en un párrafo que contenga otros elementos de texto. Puedes crear múltiples`Run` objetos para representar diferentes partes del párrafo, luego use etiquetas de código en línea para formatear solo las partes específicas como código en línea. Luego puedes agregarlos al párrafo usando el`Paragraph.AppendChild(run)` método.