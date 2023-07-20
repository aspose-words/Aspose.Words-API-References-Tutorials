---
title: Texto en negrita
linktitle: Texto en negrita
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a poner texto en negrita con Aspose.Words para la guía paso a paso de .NET.
type: docs
weight: 10
url: /es/net/working-with-markdown/bold-text/
---

En este ejemplo, le diremos cómo poner texto en negrita con Aspose.Words para .NET. El texto en negrita lo hace más visible y le da más protagonismo.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 2: texto en negrita

 Podemos poner el texto en negrita configurando el generador de documentos`Font.Bold` propiedad a`true`.

```csharp
builder.Font.Bold = true;
```

## Paso 3: Agregar contenido al documento

 Ahora podemos agregar contenido al documento utilizando los métodos del generador de documentos, como`Writeln`, que añade una línea de texto.

```csharp
builder.Writeln("This text will be bold");
```

## Ejemplo de código fuente para texto en negrita usando Aspose.Words para .NET


```csharp
// Use un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// Pon el texto en negrita.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

¡Felicidades! Ahora ha aprendido a poner texto en negrita con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo puedo hacer que el texto esté en negrita en Aspose.Words?

 R: Para poner el texto en negrita en Aspose.Words, puede usar el`Font.Bold` propiedad de la`Run`objeto. Puede establecer esta propiedad en`true` al texto específico en negrita. Por ejemplo, puedes usar`run.Font.Bold=true` poner en negrita el texto dentro del`Run` objeto.

#### P: ¿Es posible poner en negrita varios fragmentos de texto en el mismo párrafo?

 R: Sí, puede poner en negrita varios fragmentos de texto en un solo párrafo usando varias`Run` objetos. Puedes crear múltiples`Run` objetos y establecer el`Font.Bold` propiedad a`true` para cada objeto para poner en negrita las partes deseadas del texto. Luego puede agregarlos al párrafo usando el`Paragraph.AppendChild(run)` método.

#### P: ¿Puedo poner en negrita el texto que está en una tabla o celda en Aspose.Words?

 R: Sí, puede poner en negrita el texto que está en una tabla o celda en Aspose.Words. Puede navegar a la celda o párrafo que desee utilizando los métodos apropiados y luego aplicar el formato de negrita con el`Font.Bold` propiedad de la`Run` o`Paragraph` objeto.