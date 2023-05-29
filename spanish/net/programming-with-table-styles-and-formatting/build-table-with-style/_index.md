---
title: Construye una mesa con estilo
linktitle: Construye una mesa con estilo
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para construir una tabla con un estilo personalizado usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para crear una tabla con estilo usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo crear una tabla con un estilo personalizado en sus documentos de Word usando Aspose.Words para .NET.

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

## Paso 3: Inicie una nueva tabla e inserte una celda
 Para empezar a construir la tabla, usamos el`StartTable()` método del generador de documentos, luego insertamos una celda en la tabla usando el`InsertCell()` método.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Paso 4: Define el estilo de la tabla
 Ahora podemos configurar el estilo de la tabla usando el`StyleIdentifier` propiedad. En este ejemplo, estamos usando el estilo "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Paso 5: Aplicar opciones de estilo a la tabla
 Podemos especificar qué características deben ser formateadas por el estilo usando el`StyleOptions`propiedad de la matriz. En este ejemplo, aplicamos las siguientes opciones: "FirstColumn", "RowBands" y "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Paso 6: ajusta automáticamente el tamaño de la mesa
 Para ajustar automáticamente el tamaño de la matriz en función de su contenido, utilizamos el`AutoFit()` método con el`AutoFitBehavior.AutoFitToContents` comportamiento.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Paso 7: Agregar contenido a las celdas
 Ahora podemos agregar contenido a las celdas usando el`Writeln()` y`InsertCell()` métodos del generador de documentos. En este ejemplo, agregamos los encabezados para "Artículo" y "Cantidad (

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

## Paso 8: Guarde el documento modificado
Finalmente, guardamos el documento modificado en un archivo. Puede elegir un nombre y una ubicación apropiados para el documento de salida.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

¡Felicidades! Ahora ha creado una tabla con estilo personalizado utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para Build Table With Style usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Debemos insertar al menos una fila primero antes de configurar cualquier formato de tabla.
	builder.InsertCell();
	// Establezca el estilo de tabla utilizado en función del identificador de estilo único.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Aplicar qué características deben ser formateadas por el estilo.
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
En este tutorial, aprendimos a crear una tabla con estilo usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede personalizar fácilmente el estilo de sus tablas en sus documentos de Word. Aspose.Words ofrece una API poderosa y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, puede mejorar la presentación visual de sus documentos de Word y satisfacer necesidades específicas.