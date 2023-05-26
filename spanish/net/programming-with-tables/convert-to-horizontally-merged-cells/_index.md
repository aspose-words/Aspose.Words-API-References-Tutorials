---
title: Convertir a celdas combinadas horizontalmente
linktitle: Convertir a celdas combinadas horizontalmente
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir celdas de tabla en celdas combinadas horizontalmente en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

En este tutorial, aprenderemos a usar Aspose.Words para .NET para convertir celdas de tabla en celdas combinadas horizontalmente en un documento de Word. Seguiremos una guía paso a paso para comprender el código e implementar esta característica. Al final de este tutorial, podrá manipular las celdas de la tabla en sus documentos de Word mediante programación.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Cargar el documento y acceder a la tabla
Para empezar a trabajar con la tabla, necesitamos cargar el documento que la contiene y acceder a ella. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Cargue el documento
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Acceso a la matriz
Table table = doc.FirstSection.Body.Tables[0];
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos. Además, asegúrese de que el documento contenga una tabla con celdas combinadas horizontalmente.

## Paso 3: convertir a celdas combinadas horizontalmente
 A continuación, convertiremos las celdas de la tabla en celdas combinadas horizontalmente usando el`ConvertToHorizontallyMergedCells()` método. Usa el siguiente código:

```csharp
// Convertir a celdas combinadas horizontalmente
table. ConvertToHorizontallyMergedCells();
```

 Aquí solo llamamos a la`ConvertToHorizontallyMergedCells()` método en la matriz para realizar la conversión.

### Ejemplo de código fuente para convertir a celdas combinadas horizontalmente usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Ahora las celdas combinadas tienen banderas de combinación apropiadas.
	table.ConvertToHorizontallyMergedCells();
```

## Conclusión
En este tutorial, aprendimos cómo convertir celdas de tabla en celdas combinadas horizontalmente en un documento de Word usando Aspose.Words para .NET. Al seguir esta guía paso a paso e implementar el código C# provisto, puede manipular las celdas de la tabla en sus documentos de Word mediante programación. Esta característica le permite administrar y organizar sus datos de forma flexible y personalizada en una tabla.