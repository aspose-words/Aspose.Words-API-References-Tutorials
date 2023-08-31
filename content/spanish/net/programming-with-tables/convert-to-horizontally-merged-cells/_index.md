---
title: Convertir a celdas fusionadas horizontalmente
linktitle: Convertir a celdas fusionadas horizontalmente
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a convertir celdas de una tabla en celdas fusionadas horizontalmente en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

En este tutorial, aprenderemos cómo usar Aspose.Words para .NET para convertir celdas de una tabla en celdas fusionadas horizontalmente en un documento de Word. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá manipular celdas de tablas en sus documentos de Word mediante programación.

## Paso 1: configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: cargar el documento y acceder a la tabla
Para iniciar el procesamiento de textos con la tabla, debemos cargar el documento que la contiene y acceder a ella. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Acceso a la matriz
Table table = doc.FirstSection.Body.Tables[0];
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos. Además, asegúrese de que el documento contenga una tabla con celdas fusionadas horizontalmente.

## Paso 3: convertir a celdas fusionadas horizontalmente
 A continuación, convertiremos las celdas de la tabla en celdas fusionadas horizontalmente usando el`ConvertToHorizontallyMergedCells()` método. Utilice el siguiente código:

```csharp
// Convertir a celdas fusionadas horizontalmente
table. ConvertToHorizontallyMergedCells();
```

 Aquí simplemente llamamos al`ConvertToHorizontallyMergedCells()` método en la matriz para realizar la conversión.

### Código fuente de muestra para convertir a celdas fusionadas horizontalmente usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Ahora las celdas fusionadas tienen indicadores de combinación apropiados.
	table.ConvertToHorizontallyMergedCells();
```

## Conclusión
En este tutorial, aprendimos cómo convertir celdas de una tabla en celdas fusionadas horizontalmente en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# proporcionado, puede manipular las celdas de la tabla en sus documentos de Word mediante programación. Esta característica le permite administrar y organizar sus datos de forma flexible y personalizada en una tabla.