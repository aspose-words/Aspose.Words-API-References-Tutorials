---
title: Tachado
linktitle: Tachado
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a aplicar el estilo de texto tachado con la guía paso a paso de Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/strikethrough/
---


En este ejemplo, le mostraremos cómo aplicar el estilo de texto tachado usando Aspose.Words para .NET. El texto tachado se utiliza para indicar que el texto se elimina o ya no es válido.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: aplicar estilo de texto tachado

Habilitaremos el estilo de texto tachado configurando el`StrikeThrough` propiedad de la`Font` oponerse a`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Paso 3: agregue texto tachado

 Ahora podemos agregar texto tachado usando la función del generador de documentos.`Writeln` método.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Código fuente de ejemplo para texto tachado con Aspose.Words para .NET

```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// Haz que el texto esté tachado.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

¡Enhorabuena! Ahora ha aprendido cómo aplicar el estilo de texto tachado con Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Cómo puedo agregar el texto tachado en Aspose.Words?

 R: Para agregar el texto tachado en Aspose.Words, puede usar el`Font.StrikeThrough` propiedad de la`Run`objeto. Puede establecer esta propiedad en`true` para agregar texto tachado a un texto específico. Por ejemplo, puedes usar`run.Font.StrikeThrough=true` para agregar el texto tachado en el`Run` objeto.

#### P: ¿Es posible agregar texto tachado a varios fragmentos de texto en el mismo párrafo?

 R: Sí, puedes agregar texto tachado a varias partes del texto en un solo párrafo usando múltiples`Run` objetos. Puedes crear múltiples`Run` objetos y establecer el`Font.StrikeThrough`propiedad a`true` para cada objeto para agregar el texto tachado a las partes de texto deseadas. Luego puedes agregarlos al párrafo usando el`Paragraph.AppendChild(run)` método.

#### P: ¿Puedo agregar texto tachado al texto que está en una tabla o celda en Aspose.Words?

 R: Sí, puede agregar texto tachado al texto que se encuentra en una tabla o celda en Aspose.Words. Puede saltar a la celda o párrafo que desee utilizando los métodos adecuados y luego aplicar el formato de texto tachado utilizando el`Font.StrikeThrough` propiedad de la`Run` o`Paragraph` objeto.