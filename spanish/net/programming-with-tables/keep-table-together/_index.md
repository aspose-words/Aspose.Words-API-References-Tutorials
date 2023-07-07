---
title: Mantener la mesa unida
linktitle: Mantener la mesa unida
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a mantener unida una tabla en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-tables/keep-table-together/
---

En este tutorial, vamos a aprender cómo mantener unida una tabla en un documento de Word usando Aspose.Words para .NET. Seguiremos una guía paso a paso para comprender el código e implementar esta función. Al final de este tutorial, podrá mantener una tabla intacta sin que se divida en varias páginas en sus documentos de Word.

## Paso 1: Configuración del proyecto
1. Inicie Visual Studio y cree un nuevo proyecto de C#.
2. Agregue una referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: Cargar el documento y recuperar la tabla
Para comenzar a trabajar con la tabla, debemos cargar el documento y buscar la tabla que queremos mantener unida. Sigue estos pasos:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Cargue el documento
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// recuperar la mesa
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 3: habilite la opción "KeepWithNext"
Para mantener la tabla unida y evitar que se divida en varias páginas, debemos habilitar la opción "KeepWithNext" para cada párrafo de la tabla, excepto los últimos párrafos de la última fila de la tabla. Usa el siguiente código:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Aquí recorremos cada celda de la tabla y habilitamos la opción "KeepWithNext" para cada párrafo de la celda, excepto los últimos párrafos de la última fila de la tabla.

## Paso 4: Guardar el documento modificado
Finalmente, necesitamos guardar el documento modificado con la tabla unida. Usa el siguiente código:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Asegúrese de especificar la ruta y el nombre de archivo correctos para el documento de salida.

### Ejemplo de código fuente para Keep Table Together usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Necesitamos habilitar KeepWithNext para cada párrafo de la tabla para evitar que se rompa en una página,
	// excepto los últimos párrafos de la última fila de la tabla.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Conclusión
En este tutorial, aprendimos cómo mantener unida una tabla en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso e implementa el código C# provisto, puede mantener una tabla intacta y evitar que se divida en varias páginas de sus documentos. Esta característica le brinda más control sobre la apariencia y el diseño de sus tablas en sus documentos.