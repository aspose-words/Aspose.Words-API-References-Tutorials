---
title: Texto en negrita
linktitle: Texto en negrita
second_title: API de procesamiento de documentos Aspose.Words
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

 Podemos poner el texto en negrita configurando el valor del generador de documentos.`Font.Bold`propiedad a`true`.

```csharp
builder.Font.Bold = true;
```

## Paso 3: agregar contenido al documento

 Ahora podemos agregar contenido al documento usando los métodos del generador de documentos, como`Writeln`, que agrega una línea de texto.

```csharp
builder.Writeln("This text will be bold");
```

## Ejemplo de código fuente para texto en negrita usando Aspose.Words para .NET


```csharp
// Utilice un generador de documentos para agregar contenido al documento.
DocumentBuilder builder = new DocumentBuilder();

// Pon el texto en negrita.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

¡Enhorabuena! Ahora ha aprendido a poner texto en negrita con Aspose.Words para .NET.


### Preguntas frecuentes

#### P: ¿Cómo puedo poner el texto en negrita en Aspose.Words?

 R: Para poner el texto en negrita en Aspose.Words, puede utilizar el`Font.Bold` propiedad de la`Run` objeto. Puede establecer esta propiedad en`true` a texto específico en negrita. Por ejemplo, puedes usar`run.Font.Bold=true` poner en negrita el texto dentro del`Run` objeto.

#### P: ¿Es posible poner en negrita varios fragmentos de texto en el mismo párrafo?

R: Sí, puedes poner en negrita varios fragmentos de texto en un solo párrafo usando múltiples`Run` objetos. Puedes crear múltiples`Run` objetos y establecer el`Font.Bold`propiedad a`true` para cada objeto, ponga en negrita las partes deseadas del texto. Luego puedes agregarlos al párrafo usando el`Paragraph.AppendChild(run)` método.

#### P: ¿Puedo poner en negrita el texto de una tabla o celda en Aspose.Words?

 R: Sí, puede poner en negrita el texto que se encuentra en una tabla o celda en Aspose.Words. Puede navegar a la celda o párrafo que desee utilizando los métodos adecuados y luego aplicar el formato en negrita utilizando el`Font.Bold` propiedad de la`Run` o`Paragraph` objeto.