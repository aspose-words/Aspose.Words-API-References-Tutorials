---
title: Cita
linktitle: Cita
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar las comillas con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/quote/
---

En este ejemplo, explicaremos cómo utilizar la función de comillas con Aspose. Words for .NET Quote se utiliza para resaltar secciones de texto rodeándolas con un borde especial.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: usar el estilo de cita predeterminado

Usaremos el estilo de párrafo predeterminado llamado "Cita" para aplicar el formato de cita al texto.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Paso 3: Crear estilos para niveles anidados

 Podemos crear estilos para niveles anidados usando el`Styles.Add` metodo de la`Document` objeto. En este ejemplo, estamos creando un estilo llamado "Quote1" para representar un nivel de cotización anidado.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Ejemplo de código fuente para citas con Aspose.Words para .NET


```csharp
// Use un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// De forma predeterminada, un documento almacena el estilo de comillas en bloque para el primer nivel.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Cree estilos para niveles anidados a través de la herencia de estilos.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

¡Felicidades! Ahora ha aprendido a usar la función de citas con Aspose.Words para .NET.

