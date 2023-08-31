---
title: Obtener espaciado de línea de fuente
linktitle: Obtener espaciado de línea de fuente
second_title: API de procesamiento de documentos de Aspose.Words
description: En este tutorial, aprenda cómo obtener el espacio entre líneas de fuente en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/get-font-line-spacing/
---
En este tutorial, le diremos cómo obtener el espacio entre líneas de fuente en un documento de Word utilizando la biblioteca Aspose.Words para .NET. El interlineado de la fuente define el espacio vertical entre líneas de texto. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: Crear un nuevo documento y generador de documentos
 Primero, crearemos un nuevo documento instanciando el`Document` class y un generador de documentos instanciando el`DocumentBuilder` clase.

```csharp
// Crear un nuevo documento
Document doc = new Document();

//Crear un generador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Configurar la fuente
 A continuación, configuraremos la fuente configurando el`Name` propiedad del generador de documentos.

```csharp
// Configurar la fuente
builder.Font.Name = "Calibri";
```

## Paso 3: Agregar texto al documento
Ahora usaremos el generador de documentos para agregar texto formateado al documento.

```csharp
// Agregar texto al documento
builder. Writen("qText");
```

## Paso 4: obtenga el espaciado de línea de fuente
 Ahora accederemos a la`Font` objeto del primer párrafo del documento y recuperar el valor del`LineSpacing` propiedad.

```csharp
// Obtener el espacio entre líneas de la fuente
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Ejemplo de código fuente para Obtener espaciado entre líneas de fuentes usando Aspose.Words para .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Conclusión
En este tutorial, vimos cómo obtener el espacio entre líneas de fuente en un documento de Word con Aspose.Words para .NET. El espacio entre líneas de fuente es importante para controlar el espacio vertical entre líneas de texto. No dude en utilizar esta función para personalizar la apariencia de su texto en sus documentos.

### Preguntas frecuentes

#### P: ¿Cómo puedo cambiar el espacio entre líneas de un texto específico en un documento de Word?

R: Con Aspose.Words, puede cambiar fácilmente el espacio entre líneas de un texto específico en un documento de Word. Use la API para seleccionar el texto deseado y ajuste el espacio entre líneas especificando el valor apropiado.

#### P: ¿Es posible aplicar el espaciado exacto entre líneas en un documento de Word?

R: Sí, Aspose.Words le permite aplicar espacios exactos entre líneas en un documento de Word. Puede especificar un valor preciso para el espacio entre líneas mediante la API.

#### P: ¿Cómo puedo ajustar el espacio entre líneas para todo el documento de Word?

R: Con Aspose.Words, puede ajustar fácilmente el espacio entre líneas para todo el documento de Word. Utilice los métodos proporcionados por la API para especificar el espacio entre líneas deseado para todo el documento.

#### P: ¿Admite Aspose.Words el interlineado múltiple?

R: Sí, Aspose.Words admite espacios entre líneas múltiples en documentos de Word. Puede configurar espacios múltiples, como 1,5 veces o 2 veces el espacio normal, para las líneas de su texto.

#### P: ¿Cómo puedo evitar problemas de superposición de líneas al ajustar el espacio entre líneas?

R: Para evitar problemas de superposición de líneas al ajustar el espaciado entre líneas, asegúrese de elegir los valores de espaciado adecuados. Pruebe también la representación final de su documento para asegurarse de que el texto siga siendo legible y tenga un buen formato.