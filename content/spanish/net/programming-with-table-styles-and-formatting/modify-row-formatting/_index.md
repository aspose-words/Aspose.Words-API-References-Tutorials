---
title: Modificar el formato de fila
linktitle: Modificar el formato de fila
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para cambiar el formato de las filas de la tabla usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

En este tutorial, lo guiaremos paso a paso para cambiar el formato de una fila de la tabla usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarle a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo cambiar los bordes, la altura y el salto de línea de una fila de una tabla en sus documentos de Word usando Aspose.Words para .NET.

## Paso 1: definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Aquí es donde se encuentra su documento de Word. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: cargar el documento existente
 A continuación, debe cargar el documento de Word existente en una instancia del`Document` clase.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Paso 3: Accede a la línea a modificar
 Para cambiar el formato de una fila de la tabla, debemos navegar a la fila específica de la tabla. Usamos el`GetChild()` y`FirstRow` métodos para obtener la referencia a la primera fila de la tabla.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## Paso 4: cambiar el formato de fila
 Ahora podemos cambiar el formato de la fila usando las propiedades del`RowFormat` clase. Por ejemplo, podemos eliminar los bordes de las líneas, establecer la altura automática y permitir saltos de línea.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Código fuente de muestra para modificar el formato de fila usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Recupere la primera fila de la tabla.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## Conclusión
En este tutorial, aprendimos cómo cambiar el formato de una fila de una tabla usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede ajustar fácilmente los bordes, la altura y el salto de línea de las filas de las tablas de sus documentos de Word. Aspose.Words ofrece una API potente y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, puede personalizar el diseño visual de sus tablas según sus necesidades específicas.