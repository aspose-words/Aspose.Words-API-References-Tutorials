---
title: Crear tabla sencilla
linktitle: Crear tabla sencilla
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a crear una tabla simple en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/create-simple-table/
---

En este tutorial, vamos a aprender cómo crear una tabla simple en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta característica. Al final de este tutorial, podrá crear tablas personalizadas en sus documentos de Word mediante programación.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Creación del documento e inicialización del generador de documentos
Para comenzar a construir la tabla, necesitamos crear un nuevo documento e inicializar el generador de documentos. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear el documento e inicializar el generador de documentos
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: Construyendo la matriz
A continuación, crearemos la tabla utilizando los métodos proporcionados por el generador de documentos. Usa el siguiente código:

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

// Indicación de que la construcción de la mesa está terminada
builder. EndTable();
```

 Aquí usamos el generador de documentos para construir la tabla paso a paso. Empezamos llamando`StartTable()` para inicializar la tabla, luego use`InsertCell()` para insertar celdas y`Write()` para agregar contenido a cada celda. También usamos`EndRow()` para terminar una fila y comenzar una nueva fila. Finalmente, llamamos`EndTable()` para indicar que la construcción de la tabla está completa.

## Paso 4: Guarde el documento
Finalmente, tenemos que guardar

  el documento con la tabla creada. Usa el siguiente código:

```csharp
// Guardar el documento
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Ejemplo de código fuente para Create Simple Table usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Empieza a construir la mesa.
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
	//Señal de que hemos terminado de construir la mesa.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Conclusión
En este tutorial, aprendimos cómo crear una tabla simple en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# proporcionado, puede crear tablas personalizadas en sus documentos de Word mediante programación. Esta característica le permite formatear y organizar sus datos de una manera clara y estructurada.