---
title: Marcar columnas de tabla en un documento de Word
linktitle: Marcar columnas de tabla en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a marcar una columna de una tabla en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/bookmark-table-columns/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo usar la función Marcar columnas de tabla en la biblioteca Aspose.Words para .NET. Esta función le permite marcar una columna específica de una tabla en un documento de Word y acceder al contenido de esa columna.

## Requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: crear la tabla

 Antes de crear un marcador en una columna de la tabla, primero debemos crear la tabla usando un`DocumentBuilder` objeto. En nuestro ejemplo, creamos una tabla con dos filas y dos columnas:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## Paso 2: crear el marcador de columna

 Usamos el`StartBookmark` Método para crear un marcador en una columna específica de la tabla. En nuestro ejemplo, utilizamos el nombre "MyBookmark" para el marcador:

```csharp
builder. StartBookmark("MyBookmark");
```

## Paso 3: acceda al contenido de la columna

 Revisamos todos los marcadores del documento y mostramos sus nombres. Si un marcador es una columna, accedemos al contenido de esa columna utilizando el índice de la columna y el`GetText` método:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Código fuente de ejemplo para columnas de tabla de marcadores usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para demostrar la creación de un marcador en una columna de la tabla usando Aspose.Words para .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo utilizar la función Columnas de tabla de marcadores de Aspose.Words para .NET. Seguimos una guía paso a paso para marcar una columna específica de una tabla en un documento de Word y saltar al contenido de esa columna.

### Preguntas frecuentes sobre las columnas de la tabla de marcadores en un documento de Word

#### P: ¿Cuáles son los requisitos previos para utilizar la función "Marcadores para columnas de tabla" en Aspose.Words para .NET?

R: Para utilizar la función "Marcadores para columnas de tabla" en Aspose.Words para .NET, debe tener conocimientos básicos del lenguaje C#. También necesita un entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

#### P: ¿Cómo crear una tabla con columnas en un documento de Word usando Aspose.Words para .NET?

 R: Para crear una tabla con columnas en un documento de Word usando Aspose.Words para .NET, puede usar un`DocumentBuilder`objeto para insertar celdas y contenido en la tabla. Aquí hay un código de muestra:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### P: ¿Cómo marcar una columna de una tabla usando Aspose.Words para .NET?

 R: Para crear un marcador en una columna de la tabla usando Aspose.Words para .NET, puede usar el`StartBookmark` método de la`DocumentBuilder` objeto para iniciar el marcador en una columna de tabla específica. Aquí hay un código de muestra:

```csharp
builder.StartBookmark("MyBookmark");
```

#### P: ¿Cómo acceder al contenido de las columnas de la tabla desde el marcador usando Aspose.Words para .NET?

R: Para acceder al contenido de una columna de la tabla desde un marcador usando Aspose.Words para .NET, puede recorrer todos los marcadores en el documento, verificar si un marcador es una columna y usar el índice de la columna para acceder al contenido de esa columna. Aquí hay un código de muestra:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Haz algo con el contenido de la columna...
         }
     }
}
```

#### P: ¿Existe un límite en la cantidad de columnas que puedo crear en una tabla con marcadores de columna?

R: No existe un límite específico para la cantidad de columnas que puede crear en una tabla con marcadores de columna usando Aspose.Words para .NET. El límite depende principalmente de los recursos disponibles en su sistema y de las especificaciones del formato de archivo de Word que esté utilizando. Sin embargo, se recomienda no crear una cantidad excesiva de columnas, ya que esto puede afectar el rendimiento y la legibilidad del documento final.