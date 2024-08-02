---
title: Texto en cursiva
linktitle: Texto en cursiva
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a poner texto en cursiva con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/italic-text/
---

En este ejemplo, le explicaremos cómo utilizar la función de texto en cursiva con Aspose.Words para .NET. El texto en cursiva se utiliza para enfatizar ciertas partes de un documento.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: poner el texto en cursiva

 Podemos poner el texto en cursiva configurando la fuente`Italic`propiedad a`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Código fuente de ejemplo para texto en cursiva con Aspose.Words para .NET


```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// Pon el texto en cursiva.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

¡Enhorabuena! Ahora ha aprendido a utilizar la función de texto en cursiva con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo puedo poner texto en cursiva en Aspose.Words?

 R: Para poner texto en cursiva en Aspose.Words, puede utilizar el`Font.Italic` propiedad de la`Run` objeto. Puede establecer esta propiedad en`true` para poner en cursiva un texto específico. Por ejemplo, puedes usar`run.Font.Italic=true` poner en cursiva el texto contenido en el`Run` objeto.

#### P: ¿Es posible poner en cursiva varios fragmentos de texto en el mismo párrafo?

 R: Sí, puedes poner en cursiva varios fragmentos de texto en un solo párrafo utilizando varios`Run` objetos. Puedes crear múltiples`Run` objetos y establecer el`Font.Italic`propiedad a`true`para que cada objeto ponga en cursiva las partes deseadas del texto. Luego puedes agregarlos al párrafo usando el`Paragraph.AppendChild(run)` método.

#### P: ¿Puedo poner en cursiva el texto que está en una tabla o celda en Aspose.Words?

 R: Sí, puede poner en cursiva el texto que se encuentra en una tabla o celda en Aspose.Words. Puede navegar a la celda o párrafo que desee usando los métodos apropiados y luego aplicar formato en cursiva usando el`Font.Italic` propiedad de la`Run` o`Paragraph` objeto.