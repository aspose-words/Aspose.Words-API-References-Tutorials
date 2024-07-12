---
title: Ancla vertical
linktitle: Ancla vertical
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a colocar una forma verticalmente dentro de un documento usando la función de anclaje vertical en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-shapes/vertical-anchor/
---

Este tutorial explica cómo utilizar la función de anclaje vertical en Aspose.Words para .NET para colocar una forma verticalmente dentro de un documento. Al establecer la propiedad de anclaje vertical de una forma, puede controlar su alineación vertical en relación con el texto o la página.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"`con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cree un nuevo documento y DocumentBuilder
 Crear una nueva instancia del`Document` clase y un`DocumentBuilder` objeto de trabajar con el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: insertar y configurar una forma
 Insertar una forma en el documento usando el`InsertShape` método de la`DocumentBuilder` objeto. Establezca las dimensiones deseadas para la forma.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Paso 4: establezca el ancla vertical
Establezca la propiedad de anclaje vertical de la forma para controlar su alineación vertical. En este ejemplo, lo configuramos en "Inferior" para anclar la forma en la parte inferior del texto o página.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Paso 5: agregue contenido a la forma
 Utilizar el`MoveTo` método de la`DocumentBuilder` objeto para mover el cursor al primer párrafo de la forma. Luego, utiliza el`Write` Método para agregar contenido a la forma.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Paso 6: guarde el documento
 Guarde el documento en el directorio especificado utilizando el`Save`método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Código fuente de ejemplo para Vertical Anchor usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

¡Eso es todo! Ha utilizado con éxito la función de anclaje vertical en Aspose.Words para .NET para colocar una forma verticalmente dentro de un documento.