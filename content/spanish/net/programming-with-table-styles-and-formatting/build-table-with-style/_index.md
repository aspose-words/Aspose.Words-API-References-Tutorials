---
title: Construir mesa con estilo
linktitle: Construir mesa con estilo
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para crear una tabla con un estilo personalizado usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para crear una tabla con estilo usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarle a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo crear una tabla con un estilo personalizado en sus documentos de Word usando Aspose.Words para .NET.

## Paso 1: definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento de Word editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: cree un nuevo documento y un generador de documentos
 A continuación, debe crear una nueva instancia de`Document` clase y un constructor de documentos para ese documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: comience una nueva tabla e inserte una celda
 Para comenzar a construir la tabla, usamos el`StartTable()` método del generador de documentos, luego insertamos una celda en la tabla usando el`InsertCell()` método.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Paso 4: Definir el estilo de la mesa
 Ahora podemos configurar el estilo de la tabla usando el`StyleIdentifier` propiedad. En este ejemplo, utilizamos el estilo "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Paso 5: aplicar opciones de estilo a la tabla
 Podemos especificar qué características deben ser formateadas por el estilo usando el`StyleOptions`propiedad de la matriz. En este ejemplo, aplicamos las siguientes opciones: "FirstColumn", "RowBands" y "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Paso 6: ajustar automáticamente el tamaño de la mesa
 Para ajustar automáticamente el tamaño de la matriz en función de su contenido, utilizamos el`AutoFit()` método con el`AutoFitBehavior.AutoFitToContents` comportamiento.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Paso 7: agregar contenido a las celdas
 Ahora podemos agregar contenido a las celdas usando el`Writeln()` y`InsertCell()` métodos del creador de documentos. En este ejemplo, agregamos los encabezados para "Artículo" y "Cantidad (

kg)" y los datos correspondientes.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Paso 8: guarde el documento modificado
Finalmente, guardamos el documento modificado en un archivo. Puede elegir un nombre y una ubicación apropiados para el documento de salida.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

¡Enhorabuena! Ahora ha creado una tabla con estilo personalizado utilizando Aspose.Words para .NET.

### Código fuente de muestra para crear tabla con estilo usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Primero debemos insertar al menos una fila antes de configurar cualquier formato de tabla.
	builder.InsertCell();
	// Establezca el estilo de tabla utilizado según el identificador de estilo único.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Aplique qué características deben formatearse según el estilo.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Conclusión
En este tutorial, aprendimos cómo crear una tabla con estilo usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, podrás personalizar fácilmente el estilo de tus tablas en tus documentos de Word. Aspose.Words ofrece una API potente y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, podrás mejorar la presentación visual de tus documentos de Word y satisfacer necesidades específicas.