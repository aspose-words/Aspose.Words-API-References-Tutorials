---
title: Columnas de la tabla de marcadores
linktitle: Columnas de la tabla de marcadores
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a marcar una columna de tabla en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/bookmark-table-columns/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo usar la función de columnas de la tabla de marcadores en la biblioteca Aspose.Words para .NET. Esta función le permite marcar una columna específica de una tabla en un documento de Word y acceder al contenido de esa columna.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Crear la tabla

 Antes de crear un marcador en una columna de tabla, primero debemos crear la tabla usando un`DocumentBuilder` objeto. En nuestro ejemplo, creamos una tabla con dos filas y dos columnas:

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

## Paso 2: Crear el marcador de columna

 usamos el`StartBookmark`método para crear un marcador en una columna específica de la tabla. En nuestro ejemplo, usamos el nombre "MyBookmark" para el marcador:

```csharp
builder. StartBookmark("MyBookmark");
```

## Paso 3: Acceda al contenido de la columna

 Revisamos todos los marcadores en el documento y mostramos sus nombres. Si un marcador es una columna, accedemos al contenido de esa columna usando el índice de la columna y el`GetText` método:

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

### Ejemplo de código fuente para las columnas de la tabla de marcadores usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para demostrar cómo crear un marcador en una columna de tabla usando Aspose.Words para .NET:

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

En este artículo, exploramos el código fuente de C# para entender cómo usar la función de columnas de la tabla de marcadores de Aspose.Words para .NET. Seguimos una guía paso a paso para marcar una columna específica de una tabla en un documento de Word y saltar al contenido de esa columna.