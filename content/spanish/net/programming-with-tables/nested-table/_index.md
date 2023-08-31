---
title: Mesa anidada
linktitle: Mesa anidada
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear una tabla anidada en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/nested-table/
---

En este tutorial, aprenderemos cómo crear una tabla anidada en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá crear tablas anidadas en sus documentos de Word mediante programación.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: crear el documento e inicializar el generador de documentos
Para iniciar el procesamiento de textos con el documento y el generador de documentos, siga estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos
Document doc = new Document();

// Inicializar el generador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: construir la tabla anidada
A continuación, crearemos la tabla anidada insertando celdas en la tabla exterior y creando una nueva tabla dentro de la primera celda. Utilice el siguiente código:

```csharp
// Inserte la primera celda de la tabla exterior.
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Inserte la segunda celda de la tabla exterior.
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Terminación de la mesa exterior.
builder. EndTable();

// Pasar a la primera celda de la tabla exterior.
builder.MoveTo(cell.FirstParagraph);

// Construye la mesa interior
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Fin de la mesa interior
builder. EndTable();
```

Aquí usamos el generador de documentos para insertar celdas y contenido en la tabla exterior. Luego movemos el cursor del generador de documentos a la primera celda de la tabla exterior y construimos una nueva tabla en el interior insertando celdas y contenido.

## Paso 4: guardar el documento modificado
Finalmente, necesitamos guardar el documento modificado con la tabla anidada. Utilice el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Asegúrese de especificar la ruta y el nombre del archivo correctos para el documento de salida.

### Código fuente de muestra para tabla anidada usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Esta llamada es importante para crear una tabla anidada dentro de la primera tabla.
	// Sin esta llamada, las celdas insertadas a continuación se agregarán a la tabla exterior.
	builder.EndTable();
	// Vaya a la primera celda de la tabla exterior.
	builder.MoveTo(cell.FirstParagraph);
	// Construye la mesa interior.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Conclusión
En este tutorial, aprendimos cómo crear una tabla anidada en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede crear tablas anidadas según sus necesidades específicas en sus documentos de Word mediante programación.
