---
title: Creación de una sección de repetición de tabla asignada a una pieza Xml personalizada
linktitle: Creación de una sección de repetición de tabla asignada a una pieza Xml personalizada
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a crear una tabla con una sección repetitiva asignada a una CustomXmlPart en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Este tutorial demuestra cómo crear una tabla con una sección repetitiva asignada a una parte Xml personalizada en un documento de Word usando Aspose.Words para .NET. La sección repetitiva le permite agregar filas dinámicamente en función de los datos XML almacenados en la parte Xml personalizada.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y Procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cree un documento y DocumentBuilder
 Crear una nueva instancia de la`Document` clase y un`DocumentBuilder` para construir el contenido del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: agregar datos XML personalizados a una CustomXmlPart
 Crear un`CustomXmlPart` y agréguele datos XML personalizados. En este ejemplo, creamos una cadena XML que representa una colección de libros con sus títulos y autores.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Paso 4: Cree una tabla y una estructura de tabla
 Comience a crear una tabla usando el`StartTable` metodo de la`DocumentBuilder` . Agregue celdas de tabla y contenido usando el`InsertCell` y`Write` métodos.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Paso 5: cree la sección de repetición asignada a XML personalizado
 Crear un`StructuredDocumentTag` con`SdtType.RepeatingSection` para representar la sección repetida. Establezca el mapeo XML para la sección repetida usando el`SetMapping` metodo de la`XmlMapping` propiedad. En este ejemplo, asignamos la sección repetida a`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Paso 6: Cree el elemento de la sección de repetición y agregue celdas
 Crear un`StructuredDocumentTag` con`SdtType.RepeatingSectionItem` para representar el elemento de la sección que se repite. Añádalo como un niño a la sección de repetición.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Crear un`Row`para representar cada elemento en la sección repetida y adjuntarlo al elemento de la sección repetida.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Paso 7: agregue controles de contenido dentro de la sección de repetición
 Crear`StructuredDocumentTag` objetos con`SdtType.PlainText`

  para representar los controles de contenido de título y autor. Establezca la asignación XML para cada control de contenido mediante el`SetMapping` metodo de la`XmlMapping` propiedad. En este ejemplo, asignamos el control de título a`/books[1]/book[1]/title[1]` y el control del autor para`/books[1]/book[1]/author[1]`.

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

## Paso 8: Guarde el documento
 Guarde el documento modificado en el directorio especificado usando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Código fuente de ejemplo para la creación de una sección de repetición de tabla asignada a una pieza Xml personalizada mediante Aspose.Words para .NET 

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

¡Eso es todo! Ha creado correctamente una tabla con una sección repetitiva asignada a una CustomXmlPart en su documento de Word usando Aspose.Words para .NET.