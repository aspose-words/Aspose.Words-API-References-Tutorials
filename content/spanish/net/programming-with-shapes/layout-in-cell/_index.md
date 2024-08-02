---
title: Diseño en celda
linktitle: Diseño en celda
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo configurar el diseño en la celda usando Aspose.Words para .NET con esta guía completa. Perfecto para desarrolladores que buscan personalizar documentos de Word.
type: docs
weight: 10
url: /es/net/programming-with-shapes/layout-in-cell/
---
## Introducción

Si alguna vez ha querido ajustar el diseño de las celdas de su tabla en documentos de Word mediante programación, está en el lugar correcto. Hoy, profundizaremos en cómo configurar el diseño en la celda usando Aspose.Words para .NET. Analizaremos un ejemplo práctico, desglosándolo paso a paso para que pueda seguirlo con facilidad.

## Requisitos previos

Antes de pasar al código, asegurémonos de que tiene todo lo que necesita:

1.  Aspose.Words para .NET: asegúrese de tener instalada la biblioteca Aspose.Words para .NET. Si no lo has hecho, puedes[descarguelo aqui](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: necesitará un entorno de desarrollo configurado con .NET. Visual Studio es una excelente opción si busca recomendaciones.
3. Conocimientos básicos de C#: si bien explicaré cada paso, un conocimiento básico de C# le ayudará a seguirlo más fácilmente.
4.  Directorio de documentos: prepare una ruta de directorio donde guardará sus documentos. Nos referiremos a esto como`YOUR DOCUMENT DIRECTORY`.

## Importar espacios de nombres

Para comenzar, asegúrese de importar los espacios de nombres necesarios en su proyecto:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Dividamos el proceso en pasos manejables.

## Paso 1: crear un nuevo documento

 Primero, crearemos un nuevo documento de Word e inicializaremos un`DocumentBuilder` objeto que nos ayude a construir nuestro contenido.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: iniciar una tabla y establecer el formato de fila

Comenzaremos a construir una tabla y especificaremos la altura y la regla de altura para las filas.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## Paso 3: insertar celdas y completar con contenido

A continuación, hacemos un bucle para insertar celdas en la tabla. Por cada 7 celdas, finalizaremos la fila para crear una nueva.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Paso 4: agregue una forma de marca de agua

 Ahora, agreguemos una marca de agua a nuestro documento. Crearemos un`Shape` objeto y establecer sus propiedades.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // Muestre la forma fuera de la celda de la tabla si se colocará en una celda.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Paso 5: personaliza la apariencia de la marca de agua

Personalizaremos aún más la apariencia de la marca de agua configurando sus propiedades de color y texto.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Paso 6: Insertar marca de agua en el documento

Encontraremos la última ejecución en el documento e insertaremos la marca de agua en esa posición.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Paso 7: Optimice el documento para Word 2010

Para garantizar la compatibilidad, optimizaremos el documento para Word 2010.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## Paso 8: guarde el documento

Finalmente, guardaremos nuestro documento en el directorio especificado.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## Conclusión

¡Y ahí lo tienes! Creó exitosamente un documento de Word con un diseño de tabla personalizado y agregó una marca de agua usando Aspose.Words para .NET. Este tutorial tenía como objetivo proporcionar una guía clara paso a paso para ayudarle a comprender cada parte del proceso. Con estas habilidades, ahora puede crear documentos de Word más sofisticados y personalizados mediante programación.

## Preguntas frecuentes

### ¿Puedo usar una fuente diferente para el texto de la marca de agua?
 Sí, puedes cambiar la fuente configurando el`watermark.TextPath.FontFamily` propiedad a la fuente deseada.

### ¿Cómo ajusto la posición de la marca de agua?
 Puedes modificar el`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , y`VerticalAlignment` propiedades para ajustar la posición de la marca de agua.

### ¿Es posible utilizar una imagen en lugar de texto para la marca de agua?
 ¡Absolutamente! Puedes crear un`Shape` con el tipo`ShapeType.Image` y configurar su imagen usando el`ImageData.SetImage` método.

### ¿Puedo crear tablas con diferentes alturas de fila?
Sí, puedes establecer diferentes alturas para cada fila cambiando el`RowFormat.Height` propiedad antes de insertar celdas en esa fila.

### ¿Cómo elimino una marca de agua del documento?
 Puede eliminar la marca de agua ubicándola en la colección de formas del documento y llamando al`Remove` método.