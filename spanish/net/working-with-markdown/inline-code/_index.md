---
title: Código en línea
linktitle: Código en línea
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a codificar en línea con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/inline-code/
---

En este ejemplo, lo guiaremos a través de cómo usar la función de código en línea con Aspose.Words para .NET. El código en línea se utiliza para representar visualmente piezas de código dentro de un párrafo.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: agregue estilo para el código en línea

 Agregaremos un estilo personalizado para el código en línea usando el`Styles.Add` metodo de la`Document` objeto. En este ejemplo, estamos creando un estilo llamado "InlineCode" para el código en línea con un acento grave predeterminado.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Paso 3: Agregar código en línea

Ahora podemos agregar código en línea usando el estilo personalizado "InlineCode". En este ejemplo, agregamos dos piezas de texto con diferentes números de acentos graves.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Ejemplo de código fuente para Inline Code con Aspose.Words para .NET

```csharp
// Use un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

//Se pierde el número de backticks, se usará un backtick por defecto.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Habrá 3 backticks.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

¡Felicidades! Ahora ha aprendido a usar la funcionalidad de código en línea con Aspose.Words para .NET.

