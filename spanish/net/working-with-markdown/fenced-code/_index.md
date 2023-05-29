---
title: Código cercado
linktitle: Código cercado
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar la función de código delimitado con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/fenced-code/
---

En este ejemplo, lo guiaremos a través de cómo usar la función de código delimitado con Aspose.Words para .NET. El código delimitado se utiliza para representar bloques de código con un formato específico.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: agregar un estilo para el código delimitado

 Agregaremos un estilo personalizado para el código delimitado usando el`Styles.Add` metodo de la`Document` objeto. En este ejemplo, estamos creando un estilo llamado "FencedCode" para el código delimitado.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Paso 3: Agregar código delimitado sin información

Ahora podemos agregar un bloque de código cercado sin una cadena de información usando el estilo personalizado "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## Paso 4: Agregar código delimitado con cadena de información

También podemos agregar un bloque de código delimitado con una cadena de información usando otro estilo personalizado. En este ejemplo, estamos creando un estilo llamado "FencedCode.C#" para representar un bloque de código C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Código fuente de ejemplo para Código cercado usando Aspose.Words para .NET

```csharp
// Use un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```


