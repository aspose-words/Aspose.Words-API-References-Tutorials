---
title: Código sangrado
linktitle: Código sangrado
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar código sangrado con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/indented-code/
---

En este ejemplo, explicaremos cómo usar la función de código sangrado con Aspose.Words para .NET. El código sangrado se usa para representar visualmente bloques de código con un formato específico.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: agregue estilo para el código sangrado

 Agregaremos un estilo personalizado para el código sangrado usando el`Styles.Add` metodo de la`Document` objeto. En este ejemplo, estamos creando un estilo llamado "Código con sangría" para el código con sangría.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Paso 3: Agregar código sangrado

Ahora podemos agregar un bloque de código sangrado usando el estilo personalizado "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### Ejemplo de código fuente para código sangrado con Aspose.Words para .NET

```csharp
// Use un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

¡Felicidades! Ahora ha aprendido a usar la función de código sangrado con Aspose.Words para .NET.

