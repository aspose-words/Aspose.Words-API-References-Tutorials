---
title: Obtener espacio entre líneas de fuente
linktitle: Obtener espacio entre líneas de fuente
second_title: API de procesamiento de documentos Aspose.Words
description: En este tutorial, aprenderá cómo obtener el interlineado de fuente en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/get-font-line-spacing/
---
En este tutorial, le diremos cómo obtener el interlineado de fuente en un documento de Word usando la biblioteca Aspose.Words para .NET. El interlineado de fuente define el espacio vertical entre líneas de texto. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#.
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: crear un nuevo documento y un generador de documentos
 Primero, crearemos un nuevo documento creando una instancia del`Document` clase y un creador de documentos creando una instancia del`DocumentBuilder` clase.

```csharp
// Crear un nuevo documento
Document doc = new Document();

//Crear un generador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: configurar la fuente
 A continuación, configuraremos la fuente configurando el`Name` propiedad del generador de documentos.

```csharp
// Configurar la fuente
builder.Font.Name = "Calibri";
```

## Paso 3: agregue texto al documento
Ahora usaremos el generador de documentos para agregar texto formateado al documento.

```csharp
// Agregar texto al documento
builder. Writen("qText");
```

## Paso 4: obtenga el espaciado entre líneas de fuente
 Ahora accederemos al`Font` objeto del primer párrafo del documento y recuperar el valor del`LineSpacing` propiedad.

```csharp
// Obtener el interlineado de la fuente
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Código fuente de muestra para obtener espacio entre líneas de fuente usando Aspose.Words para .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Conclusión
En este tutorial, vimos cómo obtener el interlineado de fuente en un documento de Word con Aspose.Words para .NET. El espacio entre líneas de fuente es importante para controlar el espacio vertical entre líneas de texto. No dude en utilizar esta función para personalizar la apariencia del texto en sus documentos.

### Preguntas frecuentes

#### P: ¿Cómo puedo cambiar el interlineado de un texto específico en un documento de Word?

R: Con Aspose.Words, puede cambiar fácilmente el interlineado de un texto específico en un documento de Word. Utilice la API para seleccionar el texto deseado y ajuste el espacio entre líneas especificando el valor apropiado.

#### P: ¿Es posible aplicar un espacio exacto entre líneas en un documento de Word?

R: Sí, Aspose.Words le permite aplicar un espacio exacto entre líneas en un documento de Word. Puede especificar un valor preciso para el interlineado utilizando la API.

#### P: ¿Cómo puedo ajustar el interlineado de todo el documento de Word?

R: Con Aspose.Words, puede ajustar fácilmente el interlineado para todo el documento de Word. Utilice los métodos proporcionados por la API para especificar el espacio entre líneas deseado para todo el documento.

#### P: ¿Aspose.Words admite interlineado múltiple?

R: Sí, Aspose.Words admite interlineado múltiple en documentos de Word. Puede establecer espacios múltiples, como 1,5 veces o 2 veces el espacio normal, para las líneas de su texto.

#### P: ¿Cómo puedo evitar problemas de superposición de líneas al ajustar el interlineado?

R: Para evitar problemas de superposición de líneas al ajustar el espacio entre líneas, asegúrese de elegir valores de espaciado adecuados. Pruebe también la representación final de su documento para asegurarse de que el texto siga siendo legible y esté bien formateado.