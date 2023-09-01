---
title: Crear tabla simple
linktitle: Crear tabla simple
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear una tabla sencilla en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/create-simple-table/
---

En este tutorial, aprenderemos cómo crear una tabla simple en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá crear tablas personalizadas en sus documentos de Word mediante programación.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: crear el documento e inicializar el generador de documentos
Para comenzar a construir la tabla, necesitamos crear un nuevo documento e inicializar el generador de documentos. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento e inicialice el generador de documentos.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: construir la matriz
A continuación, crearemos la tabla utilizando los métodos proporcionados por el creador de documentos. Utilice el siguiente código:

```csharp
// Comenzar la construcción de la matriz
builder. StartTable();

// Construcción de la primera celda de la primera fila.
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Construcción de la segunda celda de la primera fila.
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Llame al siguiente método para finalizar la primera línea y comenzar una nueva línea
builder. EndRow();

// Construcción de la primera celda de la segunda fila.
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Construcción de la segunda celda de la segunda fila.
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Llame al siguiente método para finalizar la segunda línea.
builder. EndRow();

// Indicación de que la construcción de la mesa está terminada.
builder. EndTable();
```

 Aquí utilizamos el generador de documentos para construir la tabla paso a paso. Empezamos llamando`StartTable()` para inicializar la tabla, luego use`InsertCell()` para insertar celdas y`Write()` para agregar contenido a cada celda. También usamos`EndRow()` para finalizar una fila y comenzar una nueva fila. Finalmente, llamamos`EndTable()` para indicar que la construcción de la tabla está completa.

## Paso 4: guarde el documento
Finalmente, necesitamos guardar

  el documento con la tabla creada. Utilice el siguiente código:

```csharp
// guardar el documento
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Código fuente de muestra para crear una tabla simple usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Empiece a construir la mesa.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Construye la segunda celda.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Llame al siguiente método para finalizar la fila y comenzar una nueva fila.
	builder.EndRow();
	// Construye la primera celda de la segunda fila.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Construye la segunda celda.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Señala que hemos terminado de construir la mesa.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Conclusión
En este tutorial, aprendimos cómo crear una tabla simple en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede crear tablas personalizadas en sus documentos de Word mediante programación. Esta función le permite formatear y organizar sus datos de una manera estructurada y clara.