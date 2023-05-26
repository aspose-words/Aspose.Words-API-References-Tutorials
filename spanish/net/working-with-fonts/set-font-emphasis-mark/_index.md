---
title: Establecer marca de énfasis de fuente
linktitle: Establecer marca de énfasis de fuente
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a configurar el estilo de énfasis de fuente en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-font-emphasis-mark/
---

En este tutorial, le mostraremos cómo configurar el estilo de énfasis de fuente en un documento de Word usando Aspose.Words para .NET. El énfasis de fuente se utiliza para resaltar ciertas palabras o frases en el texto.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: Definir el directorio de documentos
Comience configurando la ruta del directorio a la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Crea y personaliza el documento
 Crear una instancia de la`Document` clase y un asociado`DocumentBuilder` para construir el contenido del documento. Utilizar el`Font.EmphasisMark`propiedad para establecer el estilo de énfasis de fuente en`EmphasisMark.UnderSolidCircle` . Luego usa el`Write` y`Writeln` métodos de la`DocumentBuilder` para agregar texto con el énfasis de fuente especificado.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Paso 3: Guarde el documento
 Guarde el documento usando el`Save` metodo de la`Document` con la ruta y el nombre de archivo adecuados.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Ejemplo de código fuente para Establecer marca de énfasis de fuente usando Aspose.Words para .NET 

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Conclusión
En este tutorial, aprendió cómo configurar el estilo de énfasis de fuente en un documento de Word usando Aspose.Words para .NET. Experimente con diferentes estilos de énfasis y use esta función para resaltar palabras o frases en sus documentos.
