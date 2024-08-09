---
title: Creación de una sección repetida de tabla asignada a una parte XML personalizada
linktitle: Creación de una sección repetida de tabla asignada a una parte XML personalizada
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear una tabla con una sección repetida asignada a CustomXmlPart en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---
## Introducción

En este tutorial, recorreremos el proceso de creación de una tabla con una sección repetida que se asigna a una parte XML personalizada usando Aspose.Words para .NET. Esto es particularmente útil para generar dinámicamente documentos basados en datos estructurados.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:
1.  Aspose.Words para la biblioteca .NET instalada. Puedes descargarlo desde el[Aspose sitio web](https://releases.aspose.com/words/net/).
2. Un conocimiento básico de C# y XML.

## Importar espacios de nombres

Asegúrese de incluir los espacios de nombres necesarios en su proyecto:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Tables;
```

## Paso 1: Inicializar documento y DocumentBuilder

 Primero, cree un nuevo documento e inicialice un`DocumentBuilder`:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: agregar parte XML personalizada

Agregue una parte XML personalizada al documento. Este XML contiene los datos que queremos asignar a nuestra tabla:

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
    "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
    "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Paso 3: crear la estructura de la tabla

 A continuación, utilice el`DocumentBuilder` para crear el encabezado de la tabla:

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Paso 4: crear una sección repetida

 Crear un`StructuredDocumentTag` (SDT) para la sección repetida y asígnela a los datos XML:

```csharp
StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Paso 5: crear un elemento de sección repetitiva

Cree un SDT para el elemento de la sección repetida y agréguelo a la sección repetida:

```csharp
StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Paso 6: asignar datos XML a celdas de tabla

Cree SDT para el título y el autor, asígnelos a los datos XML y agréguelos a la fila:

```csharp
StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Paso 7: guarde el documento

Finalmente, guarde el documento en el directorio especificado:

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

## Conclusión

Si sigue estos pasos, habrá creado con éxito una tabla con una sección repetida asignada a una parte XML personalizada utilizando Aspose.Words para .NET. Esto permite la generación de contenido dinámico basado en datos estructurados, lo que hace que la creación de documentos sea más flexible y poderosa.

## Preguntas frecuentes

### ¿Qué es una etiqueta de documento estructurado (SDT)?
Un SDT, también conocido como control de contenido, es una región delimitada en un documento que se utiliza para contener datos estructurados.

### ¿Puedo utilizar otros tipos de datos en la parte XML personalizada?
Sí, puede estructurar su parte XML personalizada con cualquier tipo de datos y asignarlos en consecuencia.

### ¿Cómo agrego más filas a la sección repetida?
La sección repetida replica automáticamente la estructura de filas para cada elemento en la ruta XML asignada.