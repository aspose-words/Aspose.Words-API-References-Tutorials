---
title: Expandir formato en celdas y fila desde estilo
linktitle: Expandir formato en celdas y fila desde estilo
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para expandir el formato a celdas y filas desde un estilo de tabla usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para expandir el formato a celdas y filas desde un estilo usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo aplicar formato de estilo de tabla a celdas y filas específicas en sus documentos de Word usando Aspose.Words para .NET.


## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Aquí es donde se encuentra su documento de Word. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta apropiada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento existente
 A continuación, debe cargar el documento de Word existente en una instancia del`Document` clase.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Paso 3: Ir a la primera celda de la primera tabla
 Para comenzar, debemos navegar hasta la primera celda de la primera tabla del documento. usamos el`GetChild()` y`FirstRow.FirstCell` métodos para obtener la referencia a la primera celda.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Paso 4: mostrar el formato de celda inicial
Antes de expandir los estilos de la tabla, mostramos el color de fondo actual de la celda. Debe estar vacío porque el formato actual se almacena en el estilo de la tabla.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Paso 5: expanda los estilos de tabla al formato directo
 Ahora expandimos los estilos de la tabla al formato directo usando el documento`ExpandTableStylesToDirectFormatting()` método.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Paso 6: mostrar el formato de celda después de la expansión de estilo
Ahora mostramos el color de fondo de la celda después de expandir los estilos de tabla. Se debe aplicar un color de fondo azul desde el estilo de tabla.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Ejemplo de código fuente para expandir formato en celdas y filas desde estilo usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Obtenga la primera celda de la primera tabla en el documento.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Primero imprima el color del sombreado de la celda.
	// Debe estar vacío ya que el sombreado actual se almacena en el estilo de tabla.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Ahora imprima el sombreado de celdas después de expandir los estilos de tabla.
	// Debería haberse aplicado un color de patrón de fondo azul desde el estilo de tabla.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Conclusión
En este tutorial, aprendimos cómo expandir el formato a celdas y filas desde un estilo de tabla usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede aplicar fácilmente formato de estilo de tabla a celdas y filas específicas en sus documentos de Word. Aspose.Words ofrece una API poderosa y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, puede personalizar aún más el diseño y la presentación de sus documentos de Word.