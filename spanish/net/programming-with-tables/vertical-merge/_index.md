---
title: Fusión vertical
linktitle: Fusión vertical
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a combinar verticalmente celdas en una tabla en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/vertical-merge/
---

En este tutorial, aprenderemos cómo fusionar verticalmente celdas en una tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá combinar verticalmente celdas en sus tablas en documentos de Word.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Cargar el documento
Para comenzar a trabajar con el documento, siga estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear un nuevo documento
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: Combinar celdas verticales
A continuación fusionaremos las celdas verticales en la tabla. Usa el siguiente código:

```csharp
// Insertar una celda
builder. InsertCell();

// Aplicar la fusión vertical a la primera celda.
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Insertar otra celda
builder. InsertCell();

// No aplicar combinación vertical a la celda
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Insertar una celda
builder. InsertCell();

// Aplicar la fusión vertical con la celda anterior
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Insertar otra celda
builder. InsertCell();

// No aplicar combinación vertical a la celda
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Finalizar la creación de la tabla.
builder. EndTable();
```

En este código, usamos el constructor DocumentBuilder para insertar celdas en una tabla. Aplicamos la combinación vertical a las celdas mediante la propiedad CellFormat.VerticalMerge. Usamos CellMerge.First para la primera combinación de celdas, CellMerge.Previous para combinar con la celda anterior y CellMerge.None para ninguna combinación vertical.

## Paso 4: Guardar el documento modificado
Finalmente, necesitamos guardar el documento modificado con las celdas combinadas. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Ejemplo de código fuente para Vertical Merge usando Aspose.Words para .NET 
```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Esta celda está fusionada verticalmente con la celda de arriba y debe estar vacía.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Conclusión
En este tutorial, aprendimos cómo fusionar verticalmente celdas en una tabla en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# proporcionado, puede fusionar fácilmente celdas verticales en sus tablas.