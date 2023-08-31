---
title: Combinar filas
linktitle: Combinar filas
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a combinar filas de una tabla en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/combine-rows/
---

En este tutorial, aprenderemos cómo usar Aspose.Words para .NET para combinar filas de tablas en un documento de Word. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá manipular y fusionar filas de tablas en sus documentos de Word mediante programación.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento y acceder a las tablas
Para iniciar el procesamiento de textos con tablas, necesitamos cargar el documento que las contiene y acceder a ellas. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento
Document doc = new Document(dataDir + "Tables.docx");

// Acceso a mesas
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: combinar filas de la tabla
A continuación, combinaremos las filas de la segunda tabla hasta el final de la primera tabla. Utilice el siguiente código:

```csharp
// Combinación de filas de la tabla
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Aquí utilizamos un`while` bucle para iterar sobre todas las filas de la segunda matriz y agregarlas al final de la primera matriz usando el`Add` método. A continuación, eliminamos la segunda tabla del documento usando el`Remove` método.

## Paso 4: guardar el documento modificado
Finalmente, necesitamos guardar el documento modificado con las filas de la tabla combinadas. Utilice el siguiente código:

```csharp
// Guardar el documento modificado
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Código fuente de muestra para combinar filas usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Las filas de la segunda tabla se agregarán al final de la primera tabla.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Agregar todas las filas de la tabla actual a las siguientes tablas
	// con diferente número de celdas y anchos se pueden unir en una tabla.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Conclusión
En este tutorial, aprendimos cómo combinar filas de tablas en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede manipular las filas de la tabla en sus documentos de Word mediante programación. Esta característica le permite fusionar y organizar sus datos de manera eficiente en una tabla.