---
title: Formato de tabla y celda con diferentes bordes
linktitle: Formato de tabla y celda con diferentes bordes
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para formatear tablas y celdas con diferentes bordes usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para formatear una tabla y una celda con diferentes bordes usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo aplicar bordes personalizados a tablas y celdas específicas en sus documentos de Word usando Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento de Word editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cree un nuevo documento y un generador de documentos
 A continuación, debe crear una nueva instancia de la`Document` clase y un constructor de documentos para ese documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Comience una nueva tabla y agregue celdas
Para comenzar a crear la tabla, usamos el`StartTable()` método del generador de documentos, luego agregamos celdas a la tabla usando el`InsertCell()` y escribimos el contenido de las celdas en el usando el`Writeln()` método.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Establecer bordes para toda la tabla.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Establecer relleno para esta celda.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Especifique un relleno de celda diferente para la segunda celda.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Borrar el formato de celda de operaciones anteriores.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Cree bordes más gruesos para la primera celda de esta fila. será diferente
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

## Paso 4: Guarde el documento

  modificado
Finalmente guarde el documento modificado en un archivo. Puede elegir un nombre y una ubicación apropiados para el documento de salida.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

¡Felicidades! Ahora ha formateado una tabla y una celda con diferentes bordes utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para formato de tabla y celda con diferentes bordes usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Establezca los bordes para toda la tabla.
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
	// Cree bordes más grandes para la primera celda de esta fila. esto sera diferente
	// en comparación con los bordes establecidos para la tabla.
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
En este tutorial, aprendimos cómo formatear una tabla y una celda con diferentes bordes usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede personalizar fácilmente los bordes de su tabla y celda en sus documentos de Word. Aspose.Words ofrece una API poderosa y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, puede mejorar la presentación visual de sus documentos de Word y satisfacer necesidades específicas.