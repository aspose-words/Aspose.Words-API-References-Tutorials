---
title: Obtener espaciado de línea de fuente
linktitle: Obtener espaciado de línea de fuente
second_title: Referencia de API de Aspose.Words para .NET
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

// Crear un generador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Configurar la fuente
 A continuación, configuraremos la fuente configurando el`Name` propiedad del generador de documentos.

```csharp
//Configurar la fuente
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
