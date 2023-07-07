---
title: Reemplazar texto en la tabla
linktitle: Reemplazar texto en la tabla
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a reemplazar texto en una tabla en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/find-and-replace-text/replace-text-in-table/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo usar la función Reemplazar texto en tabla en la biblioteca Aspose.Words para .NET. Esta característica le permite buscar y reemplazar texto específico dentro de una tabla en un documento de Word.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Cargue el documento

 Antes de comenzar a usar el reemplazo de texto en una tabla, debemos cargar el documento en Aspose.Words para .NET. Esto se puede hacer usando el`Document` class y especificando la ruta del archivo del documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## Paso 2: Accede al tablero

 Una vez cargado el documento, debemos navegar a la tabla donde queremos realizar el reemplazo de texto. En nuestro ejemplo, usamos el`GetChild` método con el`NodeType.Table` parámetro para obtener la primera tabla en el documento:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Paso 3: Realice el reemplazo de texto

 Ahora usamos el`Range.Replace` método para realizar el reemplazo de texto en la matriz. En nuestro ejemplo, reemplazamos todas las ocurrencias de la palabra "Zanahorias" con "Huevos" usando el`FindReplaceOptions` opción con la`FindReplaceDirection.Forward` dirección de búsqueda. Adicionalmente, reemplazamos el valor "50" por "20" en la última celda de la última fila de la tabla:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Paso 4: Guarda el documento editado

 Finalmente, guardamos el documento modificado en un directorio específico usando el`Save` método:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words para .NET Seguimos una guía paso a paso para cargar un documento, acceder a la tabla, realizar el reemplazo de texto y guardar el documento modificado.

### Ejemplo de código fuente para Reemplazar texto en tabla usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para demostrar el uso del reemplazo de texto en una tabla con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Tables.docx");

	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
	table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
    
```

## Conclusión

En este artículo, exploramos el código fuente de C# para entender cómo usar la función Reemplazar texto en tabla de Aspose.
