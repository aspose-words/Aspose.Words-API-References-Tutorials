---
title: Cita
linktitle: Cita
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar la cotización con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/quote/
---

En este ejemplo, explicaremos cómo utilizar la función de comillas con Aspose. Las palabras para .NET Quote se utilizan para resaltar secciones de texto rodeándolas con un borde especial.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: usar el estilo de cita predeterminado

Usaremos el estilo de párrafo predeterminado llamado "Cita" para aplicar formato de cita al texto.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Paso 3: crear estilos para niveles anidados

 Podemos crear estilos para niveles anidados usando el`Styles.Add` método de la`Document` objeto. En este ejemplo, estamos creando un estilo llamado "Cotización1" para representar un nivel de cotización anidado.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Código fuente de ejemplo para citas con Aspose.Words para .NET


```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// De forma predeterminada, un documento almacena el estilo de cita en bloque para el primer nivel.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Cree estilos para niveles anidados mediante la herencia de estilos.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

¡Enhorabuena! Ahora ha aprendido a utilizar la función de citas con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Qué es una cita en Markdown?

R: Una cita en Markdown es una forma de resaltar pasajes de texto de otras fuentes o de hacer referencia a citas famosas.

#### P: ¿Cómo utilizar comillas en Markdown?

R: Para utilizar una cita en Markdown, incluya el texto de la cita entre corchetes angulares (`>`). Cada línea de la cita debe comenzar con un galón.

#### P: ¿Las cotizaciones de Markdown admiten atributos?

R: Las citas de Markdown no admiten atributos específicos. Simplemente se resaltan por el formato del texto citado.

#### P: ¿Se pueden insertar comillas en Markdown?

R: Sí, es posible anidar comillas en Markdown agregando un nivel adicional de corchetes angulares (`>`).