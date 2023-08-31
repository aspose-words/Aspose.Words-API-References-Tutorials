---
title: Código vallado
linktitle: Código vallado
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar la función de código delimitado con la guía paso a paso de Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/fenced-code/
---

En este ejemplo, le explicaremos cómo utilizar la función de código delimitado con Aspose.Words para .NET. El código delimitado se utiliza para representar bloques de código con un formato específico.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: agregar un estilo para el código delimitado

 Agregaremos un estilo personalizado para el código cercado usando el`Styles.Add` método de la`Document` objeto. En este ejemplo, estamos creando un estilo llamado "FencedCode" para el código delimitado.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Paso 3: agregar código delimitado sin información

Ahora podemos agregar un bloque de código delimitado sin cadena de información utilizando el estilo personalizado "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## Paso 4: agregue código delimitado con cadena de información

También podemos agregar un bloque de código delimitado con una cadena de información usando otro estilo personalizado. En este ejemplo, estamos creando un estilo llamado "FencedCode.C#" para representar un bloque de código C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Código fuente de ejemplo para código protegido usando Aspose.Words para .NET

```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Preguntas frecuentes

#### P: ¿Qué es el código delimitado en Markdown?

R: El código delimitado en Markdown es un método de formato utilizado para mostrar código en un documento de Markdown. Consiste en enmarcar el código con delimitadores específicos.

#### P: ¿Cuáles son los beneficios del código delimitado en Markdown?

R: El código delimitado en Markdown mejora la legibilidad del código y lo hace más fácil de entender para los lectores. También permite preservar el resaltado de sintaxis en algunos editores de Markdown.

#### P: ¿Cuál es la diferencia entre código delimitado y con sangría en Markdown?

R: El código delimitado utiliza delimitadores específicos para encerrar el código, mientras que el código sangrado implica sangrar cada línea de código con espacios o tabulaciones.

#### P: ¿Todos los editores de Markdown admiten el código delimitado en Markdown?

R: La compatibilidad con código delimitado en Markdown puede variar entre los editores de Markdown. Consulte la documentación específica de su editor para estar seguro.

