---
title: Código sangrado
linktitle: Código sangrado
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar código con sangría con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/indented-code/
---

En este ejemplo, explicaremos cómo utilizar la función de código con sangría con Aspose.Words para .NET. El código sangrado se utiliza para representar visualmente bloques de código con un formato específico.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: agregar estilo al código con sangría

 Agregaremos un estilo personalizado para el código sangrado usando el`Styles.Add` método de la`Document` objeto. En este ejemplo, estamos creando un estilo llamado "IndentedCode" para código sangrado.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Paso 3: agregar código con sangría

Ahora podemos agregar un bloque de código sangrado usando el estilo personalizado "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### Código fuente de ejemplo para código sangrado con Aspose.Words para .NET

```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

¡Enhorabuena! Ahora ha aprendido a utilizar la función de código con sangría con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Qué es el código con sangría en Markdown?

R: El código con sangría en Markdown es un método de formato que se utiliza para mostrar código en un documento de Markdown. Consiste en sangrar cada línea de código con espacios o tabulaciones.

#### P: ¿Cómo utilizar código con sangría en Markdown?

R: Para usar código con sangría en Markdown, sangra cada línea de código con espacios o tabulaciones.

#### P: ¿Cuáles son las ventajas del código con sangría en Markdown?

R: El código sangrado en Markdown mejora la legibilidad del código y lo hace más fácil de entender para los lectores.

#### P: ¿Cuál es la diferencia entre código con sangría y bloques de código en Markdown?

R: El código con sangría se usa para pequeños fragmentos de código insertados en el texto, mientras que los bloques de código se usan para mostrar fragmentos de código más grandes en formatos separados.

#### P: ¿Todos los editores de Markdown admiten el código con sangría en Markdown?

R: La compatibilidad con código con sangría en Markdown puede variar entre los editores de Markdown. Consulte la documentación específica de su editor para estar seguro.