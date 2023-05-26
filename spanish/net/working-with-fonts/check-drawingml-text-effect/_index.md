---
title: Compruebe el efecto de texto DrawingML
linktitle: Compruebe el efecto de texto DrawingML
second_title: Referencia de API de Aspose.Words para .NET
description: En este tutorial, aprenda a comprobar los efectos de texto de DrawingML en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/check-drawingml-text-effect/
---

En este tutorial, lo guiaremos a través de cómo verificar los efectos de texto de DrawingML en un documento de Word usando Aspose.Words Library para .NET. Verificar los efectos de texto de DrawingML le permite determinar si un efecto específico se aplica a una parte del texto. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto
- Un documento de Word que contiene efectos de texto DrawingML

## Paso 1: Definir el directorio de documentos
 Primero, debe establecer la ruta del directorio en la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento y verifique los efectos de texto
continuación, cargaremos el documento de Word y accederemos a la colección de ejecuciones (secuencias de caracteres) en el primer párrafo del cuerpo del documento. A continuación, comprobaremos si se aplican efectos de texto específicos de DrawingML a la fuente de la primera ejecución.

```csharp
//Cargue el documento
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Compruebe los efectos de texto de DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Ejemplo de código fuente para verificar el efecto DMLText usando Aspose.Words para .NET 

```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Una ejecución puede tener varios efectos de texto Dml aplicados.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Conclusión
En este tutorial, vimos cómo verificar los efectos de texto de DrawingML en un documento de Word usando Aspose.Words para .NET. Verificar los efectos de texto de DrawingML le permite identificar partes del texto que tienen efectos específicos aplicados. Siéntase libre de usar esta función para manipular y analizar efectos de texto en sus documentos de Word.
