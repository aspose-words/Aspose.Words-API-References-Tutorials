---
title: Tabla formateada
linktitle: Tabla formateada
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear una tabla formateada en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/formatted-table/
---

En este tutorial, aprenderemos cómo crear una tabla formateada en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá crear tablas con formato personalizado en sus documentos de Word mediante programación.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: crear el documento e inicializar el generador de documentos
Para comenzar a construir la tabla formateada, necesitamos crear un nuevo documento e inicializar el generador de documentos. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento e inicialice el generador de documentos.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: crear la tabla formateada
continuación, crearemos la tabla formateada utilizando los métodos proporcionados por el creador de documentos. Utilice el siguiente código:

```csharp
// Comenzar la construcción de la matriz
Table table = builder. StartTable();

// Construcción de la fila del encabezado de la tabla.
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Construcción del cuerpo de la matriz.
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Fin de la construcción del conjunto.
builder. EndTable();
```

 Aquí utilizamos el generador de documentos para construir la tabla paso a paso. Empezamos llamando`StartTable()` para inicializar la tabla. Entonces usamos`InsertCell()` para insertar celdas y`Write()` para agregar contenido a cada celda. También utilizamos diferentes propiedades de formato para definir el formato de las filas, celdas y texto de la tabla.

## Paso 4: guarde el documento
Finalmente, necesitamos guardar el documento que contiene la tabla formateada. Utilice el siguiente código:

```csharp
// guardar el documento
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Código fuente de muestra para tabla formateada usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// El formato para toda la tabla se debe aplicar después de que al menos una fila esté presente en la tabla.
	table.LeftIndent = 20.0;
	// Establezca la altura y defina la regla de altura para la fila del encabezado.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// No necesitamos especificar el ancho de esta celda porque se hereda de la celda anterior.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Restablezca la altura y defina una regla de altura diferente para el cuerpo de la tabla.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Restablecer el formato de fuente.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Conclusión
En este tutorial, aprendimos cómo crear una tabla formateada en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede crear tablas personalizadas con formato específico en sus documentos de Word mediante programación. Esta función le permite presentar y estructurar sus datos de una manera visualmente atractiva y organizada.