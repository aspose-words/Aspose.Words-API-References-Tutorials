---
title: Establecer relleno de celda
linktitle: Establecer relleno de celda
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para configurar los márgenes de las celdas de las tablas con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para configurar los márgenes de las celdas de la tabla usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo ajustar los márgenes (espacio) izquierdo, superior, derecho e inferior del contenido de las celdas en sus tablas en sus documentos de Word usando Aspose.Words para .NET.

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
builder. StartTable();
builder. InsertCell();
```

## Paso 4: establece los márgenes de las celdas
 Ahora podemos establecer los márgenes de las celdas usando el`SetPaddings()` metodo de la`CellFormat` objeto. Los márgenes se definen en puntos y se especifican en el orden izquierdo, superior, derecho e inferior.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## Paso 5: Agregar contenido a la celda
 Luego podemos agregar contenido a la celda usando el generador de documentos`Writeln()` método.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Paso 6: Termina la tabla y guarda el documento
 Finalmente, terminamos de crear la tabla usando el`EndRow()` método y`EndTable()`, luego guardamos el documento modificado en un archivo.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Ejemplo de código fuente para Establecer relleno de celda usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Establece la cantidad de espacio (en puntos) para agregar a la izquierda/arriba/derecha/abajo del contenido de la celda.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Conclusión
En este tutorial, aprendimos cómo configurar los márgenes de una celda de tabla usando Aspose.Words para .NET. Al seguir esta guía paso a paso, puede ajustar fácilmente los márgenes de las celdas para crear espacios a la izquierda, arriba, a la derecha y al final del contenido de sus tablas en sus documentos de Word. Aspose.Words ofrece una API poderosa y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, puede personalizar el formato de sus tablas según sus necesidades específicas.