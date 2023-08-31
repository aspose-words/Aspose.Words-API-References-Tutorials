---
title: Compruebe el efecto de texto DrawingML
linktitle: Compruebe el efecto de texto DrawingML
second_title: API de procesamiento de documentos de Aspose.Words
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
A continuación, cargaremos el documento de Word y accederemos a la colección de ejecuciones (secuencias de caracteres) en el primer párrafo del cuerpo del documento. A continuación, comprobaremos si se aplican efectos de texto específicos de DrawingML a la fuente de la primera ejecución.

```csharp
// Cargue el documento
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

//Ruta a su directorio de documentos
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

### Preguntas frecuentes

#### P: ¿Cómo puedo acceder a los efectos de texto de DrawingML en un documento de Word usando Aspose.Words?

R: Con Aspose.Words, puede acceder a los efectos de texto de DrawingML en un documento de Word utilizando la API proporcionada. Puede explorar elementos de texto y verificar propiedades específicas de efectos de texto, como color, tamaño, etc.

#### P: ¿Qué tipos de efectos de texto DrawingML se usan comúnmente en los documentos de Word?

R: Los tipos de efectos de texto DrawingML comúnmente utilizados en documentos de Word incluyen sombras, reflejos, brillos, degradados, etc. Estos efectos se pueden aplicar para mejorar la apariencia y el formato del texto.

#### P: ¿Cómo puedo verificar el color de un efecto de texto DrawingML en un documento de Word?

R: Para comprobar el color de un efecto de texto DrawingML en un documento de Word, puede utilizar los métodos proporcionados por Aspose.Words para acceder a las propiedades de color del efecto de texto. De esta manera, puede obtener el color utilizado para el efecto de texto específico.

#### P: ¿Es posible verificar los efectos de texto en documentos de Word que contienen varias secciones?

R: Sí, Aspose.Words permite verificar los efectos de texto en documentos de Word que contienen varias secciones. Puede navegar a través de cada sección del documento y acceder a los efectos de texto para cada sección individualmente.

#### P: ¿Cómo puedo verificar la opacidad de un efecto de texto DrawingML en un documento de Word?

R: Para comprobar la opacidad de un efecto de texto DrawingML en un documento de Word, puede utilizar los métodos proporcionados por Aspose.Words para acceder a las propiedades de opacidad del efecto de texto. Esto le permitirá obtener el valor de opacidad aplicado al efecto de texto específico.