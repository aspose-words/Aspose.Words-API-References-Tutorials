---
title: Formatear tabla y celda con diferentes bordes
linktitle: Formatear tabla y celda con diferentes bordes
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para formatear tablas y celdas con diferentes bordes usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

En este tutorial, lo guiaremos paso a paso para formatear una tabla y una celda con diferentes bordes usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarle a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo aplicar bordes personalizados a tablas y celdas específicas en sus documentos de Word usando Aspose.Words para .NET.

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

## Paso 3: comience una nueva tabla y agregue celdas
Para comenzar a crear la tabla, utilizamos el`StartTable()` método del generador de documentos, luego agregamos celdas a la tabla usando el`InsertCell()` método y escribimos el contenido de las celdas usando el`Writeln()` método.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Establece bordes para toda la mesa.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Establezca el relleno para esta celda.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Especifique un relleno de celda diferente para la segunda celda.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Borre el formato de celda de operaciones anteriores.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Crea bordes más gruesos para la primera celda de esta fila. será diferente
// en relación con los bordes definidos para la tabla.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Paso 4: guarde el documento

  modificado
Finalmente guarde el documento modificado en un archivo. Puede elegir un nombre y una ubicación apropiados para el documento de salida.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

¡Enhorabuena! Ahora ha formateado una tabla y una celda con bordes diferentes usando Aspose.Words para .NET.

### Código fuente de muestra para formatear tabla y celda con diferentes bordes usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Establece los bordes de toda la tabla.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Establezca el sombreado de celda para esta celda.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// Especifique un sombreado de celda diferente para la segunda celda.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Borre el formato de celda de operaciones anteriores.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Crea bordes más grandes para la primera celda de esta fila. Esto será diferente
	// en comparación con los bordes establecidos para la mesa.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Conclusión
En este tutorial, aprendimos cómo formatear una tabla y una celda con diferentes bordes usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede personalizar fácilmente los bordes de sus tablas y celdas en sus documentos de Word. Aspose.Words ofrece una API potente y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, podrás mejorar la presentación visual de tus documentos de Word y satisfacer necesidades específicas.