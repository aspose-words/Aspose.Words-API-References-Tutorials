---
title: Configuraciones de ancho preferidas
linktitle: Configuraciones de ancho preferidas
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a establecer anchos de celda de tabla preferidos en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/preferred-width-settings/
---

En este tutorial, aprenderemos cómo establecer la configuración de ancho preferida para las celdas de una tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá especificar diferentes anchos preferidos para las celdas de su tabla en sus documentos de Word.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Creación del documento e inicialización del generador de documentos
Para comenzar a trabajar con el documento y el generador de documentos, siga estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos
Document doc = new Document();

// Inicializar el generador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: Construcción de la mesa con anchos preferidos
A continuación, construiremos una tabla con tres celdas que tengan distintos anchos preferidos. Usa el siguiente código:

```csharp
// Comienzo de la mesa
builder. StartTable();

// Insertar una celda de tamaño absoluto
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Insertar una celda de tamaño relativo (en porcentaje)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Insertar una celda de tamaño automático
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// final de la mesa
builder. EndTable();
```

Aquí usamos el generador de documentos para construir una tabla con tres celdas. La primera celda tiene un ancho preferencial de 40 puntos, la segunda celda tiene un ancho preferencial del 20 % del ancho de la tabla y la tercera celda tiene un ancho preferencial automático que se ajusta

  dependiendo del espacio disponible.

## Paso 4: Guardar el documento modificado
Finalmente, debemos guardar el documento modificado con la configuración de ancho preferida definida para las celdas de la tabla. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Ejemplo de código fuente para la configuración de ancho preferido con Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Inserte una fila de tabla compuesta por tres celdas que tengan diferentes anchos preferidos.
	builder.StartTable();
	// Inserte una celda de tamaño absoluto.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Inserte una celda de tamaño relativo (porcentaje).
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Inserta una celda de tamaño automático.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Conclusión
En este tutorial, aprendimos cómo establecer la configuración de ancho preferida para las celdas de una tabla en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# provisto, puede personalizar el ancho de las celdas de su tabla según sus necesidades específicas en sus documentos de Word.