---
title: Establecer el formato de fila de la tabla
linktitle: Establecer el formato de fila de la tabla
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para configurar el formato de fila de la tabla con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para configurar el formato de fila de la tabla usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo ajustar la altura y los rellenos de una fila de tabla en sus documentos de Word usando Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento de Word editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cree un nuevo documento y un generador de documentos
 A continuación, debe crear una nueva instancia de la`Document` clase y un constructor de documentos para ese documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Comience una nueva tabla y agregue una celda
Para comenzar a crear la tabla, usamos el`StartTable()` del constructor del documento, luego agregamos una celda a la tabla usando el`InsertCell()` método.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Paso 4: Defina el formato de línea
 Ahora podemos establecer el formato de fila accediendo a la`RowFormat` objeto de la`DocumentBuilder` objeto. Podemos establecer la altura de la línea y los márgenes (rellenos) utilizando las propiedades correspondientes.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Paso 5: establecer los márgenes de la tabla
 A continuación, podemos configurar los paddings de la tabla accediendo a las propiedades correspondientes del`Table` objeto. Estos márgenes se aplicarán a todas las filas de la tabla.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Paso 6: Agregar contenido a la fila
 Finalmente, podemos agregar contenido a la línea usando el generador de documentos`Writeln()` método.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Paso 7: Termina la tabla y guarda el documento
En

 final, terminamos de crear la tabla usando el`EndRow()` y`EndTable()` método, luego guardamos el documento modificado en un archivo.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Ejemplo de código fuente para establecer formato de fila de tabla con Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Estas propiedades de formato se establecen en la tabla y se aplican a todas las filas de la tabla.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Conclusión
En este tutorial, aprendimos cómo configurar el formato de fila de la tabla usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede ajustar fácilmente la altura y los márgenes de las filas de las tablas en sus documentos de Word. Aspose.Words ofrece una API poderosa y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, puede personalizar el diseño visual de sus tablas según sus necesidades específicas.