---
title: Creación de una sección repetida de tabla asignada a una parte XML personalizada
linktitle: Creación de una sección repetida de tabla asignada a una parte XML personalizada
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear una tabla con una sección repetida asignada a CustomXmlPart en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Este tutorial muestra cómo crear una tabla con una sección repetida asignada a un elemento XML personalizado en un documento de Word usando Aspose.Words para .NET. La sección repetida le permite agregar filas dinámicamente según los datos XML almacenados en la parte XML personalizada.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: crear un documento y DocumentBuilder
 Crear una nueva instancia del`Document` clase y un`DocumentBuilder` para construir el contenido del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: agregar datos XML personalizados a CustomXmlPart
 Crear un`CustomXmlPart` y agregarle datos XML personalizados. En este ejemplo, creamos una cadena XML que representa una colección de libros con sus títulos y autores.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Paso 4: crear una tabla y una estructura de tabla
 Comience a crear una tabla usando el`StartTable` método de la`DocumentBuilder` . Agregue celdas de tabla y contenido usando el`InsertCell` y`Write` métodos.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Paso 5: cree la sección repetida asignada a XML personalizado
 Crear un`StructuredDocumentTag` con`SdtType.RepeatingSection` para representar la sección repetida. Establezca la asignación XML para la sección repetida usando el`SetMapping` método de la`XmlMapping` propiedad. En este ejemplo, asignamos la sección repetida a`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Paso 6: cree el elemento de la sección repetida y agregue celdas
 Crear un`StructuredDocumentTag` con`SdtType.RepeatingSectionItem` para representar el elemento de la sección repetida. Agréguelo como niño a la sección repetida.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Crear un`Row`para representar cada elemento en la sección repetida y agregarlo al elemento de la sección repetida.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Paso 7: agregue controles de contenido dentro de la sección repetida
 Crear`StructuredDocumentTag` objetos con`SdtType.PlainText`

  para representar los controles de contenido del título y del autor. Establezca la asignación XML para cada control de contenido utilizando el`SetMapping` método de la`XmlMapping` propiedad. En este ejemplo, asignamos el control de título a`/books[1]/book[1]/title[1]` y el control del autor para`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Paso 8: guarde el documento
 Guarde el documento modificado en el directorio especificado utilizando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Código fuente de ejemplo para crear una sección repetida de tabla asignada a una parte XML personalizada usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

¡Eso es todo! Ha creado con éxito una tabla con una sección repetida asignada a CustomXmlPart en su documento de Word usando Aspose.Words para .NET.