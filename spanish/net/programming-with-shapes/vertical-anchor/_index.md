---
title: Anclaje Vertical
linktitle: Anclaje Vertical
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a colocar una forma verticalmente dentro de un documento utilizando la función de anclaje vertical en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-shapes/vertical-anchor/
---

Este tutorial explica cómo usar la función de anclaje vertical en Aspose.Words para .NET para colocar una forma verticalmente dentro de un documento. Al configurar la propiedad de anclaje vertical de una forma, puede controlar su alineación vertical en relación con el texto o la página.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y Procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cree un nuevo documento y DocumentBuilder
 Crear una nueva instancia de la`Document` clase y un`DocumentBuilder` objeto de trabajar con el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Insertar y configurar una forma
 Inserte una forma en el documento usando el`InsertShape` metodo de la`DocumentBuilder` objeto. Establezca las dimensiones deseadas para la forma.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Paso 4: establecer el ancla vertical
Establezca la propiedad de anclaje vertical de la forma para controlar su alineación vertical. En este ejemplo, lo configuramos en "Inferior" para anclar la forma en la parte inferior del texto o la página.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Paso 5: Agregar contenido a la forma
 Utilizar el`MoveTo` metodo de la`DocumentBuilder` objeto para mover el cursor al primer párrafo de la forma. Luego, usa el`Write` método para agregar contenido a la forma.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Paso 6: Guarde el documento
 Guarde el documento en el directorio especificado usando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Ejemplo de código fuente para Vertical Anchor usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
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