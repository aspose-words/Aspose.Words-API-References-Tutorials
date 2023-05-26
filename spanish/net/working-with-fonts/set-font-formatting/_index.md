---
title: Establecer formato de fuente
linktitle: Establecer formato de fuente
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a configurar el formato de fuente en un documento de Word usando Aspose.Words para .NET y cree documentos atractivos.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-font-formatting/
---
En este tutorial, le mostraremos cómo configurar el formato de fuente en un documento de Word usando Aspose.Words para .NET. Aprenderá a aplicar estilos como negrita, color, cursiva, fuente, tamaño, espaciado y subrayado.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: Definir el directorio de documentos
Comience configurando la ruta del directorio a la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crear y dar formato al documento
 Crear una instancia de la`Document` clase y el`DocumentBuilder` clase para construir el documento. Utilizar el`Font` propiedad de la`DocumentBuilder` para acceder a las propiedades de formato de fuente.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## Paso 3: Guarde el documento
 Utilizar el`Save` para guardar el documento con el formato de fuente aplicado. Reemplazar`"WorkingWithFonts.SetFontFormatting.docx"` con el nombre de archivo deseado.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### Ejemplo de código fuente para Establecer formato de fuente usando Aspose.Words para .NET 
```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## Conclusión
¡Felicidades! Ahora sabe cómo configurar el formato de fuente en un documento de Word usando Aspose.Words para .NET. Puede explorar más opciones de formato de fuente y crear documentos de Word personalizados y atractivos.
