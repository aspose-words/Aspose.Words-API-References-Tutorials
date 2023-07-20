---
title: Fusión Horizontal
linktitle: Fusión Horizontal
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a fusionar celdas horizontalmente en una tabla de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/horizontal-merge/
---

En este tutorial, aprenderemos cómo fusionar celdas horizontalmente en una tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta característica. Al final de este tutorial, podrá combinar celdas horizontalmente en sus tablas de Word mediante programación.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Creación del documento e inicialización del generador de documentos
Para iniciar el procesamiento de textos con la tabla y las celdas, debemos crear un nuevo documento e inicializar el generador de documentos. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear el documento e inicializar el generador de documentos
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: Construcción de la tabla con combinación horizontal de celdas
continuación, crearemos la tabla y aplicaremos la combinación de celdas horizontal utilizando las propiedades proporcionadas por Aspose.Words para .NET. Usa el siguiente código:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Esta celda se fusiona con la anterior y debe estar vacía.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Aquí usamos el generador de documentos para construir la tabla y establecer las propiedades de combinación horizontal de celdas. usamos el`HorizontalMerge` propiedad de la`CellFormat` objeto para especificar el tipo de combinación horizontal que se aplicará a cada celda. Usando`CellMerge.First` fusionamos la primera celda con la siguiente, mientras usamos`CellMerge.Previous` fusionamos la celda actual con la celda anterior.`CellMerge.None` indica que la celda no debe fusionarse.

## Paso 4: Guardar el documento modificado
Finalmente, debemos guardar el documento modificado con las celdas fusionadas horizontalmente. Usa el siguiente código:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Ejemplo de código fuente para combinación horizontal usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Esta celda se fusiona con la anterior y debe estar vacía.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Conclusión
En este tutorial, aprendimos cómo fusionar celdas horizontalmente en una tabla en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# proporcionado, puede aplicar la combinación de celdas horizontales en sus tablas de Word mediante programación. Esta característica le permite crear diseños de tablas más complejos y organizar mejor sus datos.