---
title: Insertar tabla directamente
linktitle: Insertar tabla directamente
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar una tabla directamente en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/insert-table-directly/
---

En este tutorial, aprenderemos cómo insertar directamente una tabla en un documento de Word utilizando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta característica. Al final de este tutorial, podrá insertar tablas directamente en sus documentos de Word mediante programación.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Creación del documento y la tabla
Para iniciar el procesamiento de textos con la matriz, debemos crear un nuevo documento e inicializar la matriz. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos
Document doc = new Document();

//Crear la matriz
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: Construyendo la matriz
A continuación, construiremos la tabla agregando filas y celdas. Use el siguiente código como ejemplo:

```csharp
// Crea la primera fila
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Crear la primera celda
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Duplicar la celda para la segunda celda de la fila.
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Aquí creamos una fila con el`AllowBreakAcrossPages` propiedad establecida en`true` para permitir el salto de página entre filas. Luego creamos una celda con un fondo de color, ancho fijo y contenido de texto específico. Luego duplicamos esta celda para crear la segunda celda en la fila.

## Paso 4: Tabla de ajuste automático
Podemos aplicar ajustes automáticos a la tabla para formatearla correctamente. Usa el siguiente código:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Esta línea de código aplica un ajuste automático basado en anchos de columna fijos.

## Paso 5: Registrar el

  documento modificado
Finalmente, necesitamos guardar el documento modificado con la tabla insertada directamente. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Ejemplo de código fuente para Insertar tabla directamente usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Comenzamos creando el objeto de la tabla. Tenga en cuenta que debemos pasar el objeto del documento
	//al constructor de cada nodo. Esto se debe a que cada nodo que creamos debe pertenecer
	// a algún documento.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Aquí podríamos llamar a GuaranteeMinimum para crear las filas y celdas para nosotros. Este método se utiliza
	// para asegurarse de que el nodo especificado es válido. En este caso, una tabla válida debe tener al menos una fila y una celda.
	// En su lugar, nos encargaremos de crear la fila y la tabla nosotros mismos.
	// Esta sería la mejor manera de hacer esto si estuviéramos creando una tabla dentro de un algoritmo.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Ahora podemos aplicar cualquier configuración de ajuste automático.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Luego repetiríamos el proceso para las otras celdas y filas de la tabla.
	// También podemos acelerar las cosas clonando celdas y filas existentes.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Conclusión
En este tutorial, aprendimos cómo insertar directamente una tabla en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# provisto, puede insertar tablas directamente en sus documentos de Word mediante programación. Esta característica le permite crear y personalizar tablas según sus necesidades específicas.