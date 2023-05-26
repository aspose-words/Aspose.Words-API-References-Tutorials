---
title: Formato de fuente
linktitle: Formato de fuente
second_title: Referencia de API de Aspose.Words para .NET
description: En este tutorial, aprenda a formatear la fuente en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/font-formatting/
---

En este tutorial, lo guiaremos a través de cómo dar formato a la fuente en un documento de Word utilizando la biblioteca Aspose.Words para .NET. El formato de fuente le permite personalizar la apariencia del texto, incluido el tamaño, la negrita, el color, la fuente, el subrayado y más. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: Definir el directorio de documentos
 Primero, debe establecer la ruta del directorio en la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear un nuevo documento y generador de documentos
 A continuación, crearemos un nuevo documento instanciando el`Document` class y un generador de documentos instanciando el`DocumentBuilder` clase.

```csharp
// Crear un nuevo documento
Document doc = new Document();

// Crear un generador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: configurar el formato de fuente
 Ahora accederemos a la`Font` objeto del generador de documentos y configure las propiedades de formato de fuente, como tamaño, negrita, color, fuente, subrayado, etc.

```csharp
// Accede a la fuente
Font font = builder.Font;

// Configurar formato de fuente
font.Size = 16;
font. Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
```

## Paso 4: Agregar texto al documento
A continuación, usaremos el generador de documentos para agregar texto formateado al documento.

```csharp
// Agregar texto al documento
builder.Write("Example text.");
```

## Paso 5: Guarde el documento
Finalmente, guardaremos el documento que contiene el formato de fuente.

```csharp
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

### Ejemplo de código fuente para el formato de fuente usando Aspose.Words para .NET 
```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
builder.Write("Sample text.");
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

## Conclusión
En este tutorial, vimos cómo formatear fuentes en un documento de Word usando Aspose.Words para .NET. El formato de fuente le permite personalizar la apariencia del texto en sus documentos. No dude en utilizar esta función para crear documentos atractivos y profesionales.