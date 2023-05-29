---
title: Aplicar formato de fila
linktitle: Aplicar formato de fila
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para aplicar formato de fila a una tabla usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para aplicar formato de fila a una tabla usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, comprenderá claramente cómo formatear filas de tablas en sus documentos de Word usando Aspose.Words para .NET.

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

## Paso 3: Inicie un nuevo tablero
 Para aplicar el formato de fila, primero debemos comenzar una nueva tabla usando el`StartTable()` método del constructor del documento.

```csharp
Table table = builder. StartTable();
```

## Paso 4: inserte una celda y vaya al formato de fila
Ahora podemos insertar una celda en la tabla y acceder al formato de fila para esa celda usando el generador de documentos.`InsertCell()` y`RowFormat` métodos.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Paso 5: establecer la altura de la fila
 Para establecer la altura de la fila, usamos el`Height` y`HeightRule` propiedades del formato de fila. En este ejemplo, establecemos una altura de fila de 100 puntos y usamos el`Exactly` regla.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Paso 6: Definir el formato de la tabla
 Algunas propiedades de formato se pueden establecer en la propia tabla y se aplican a todas las filas de la tabla. En este ejemplo, configuramos las propiedades del margen de la tabla usando el`LeftPadding`, `RightPadding`, `TopPadding` y`BottomPadding` propiedades.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Paso 7: Agregar contenido a la fila
Ahora podemos

 Vamos a agregar contenido a la línea utilizando los métodos del constructor de documentos. En este ejemplo, usamos el`Writeln()` método para agregar texto a la línea.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Paso 8: Terminar la línea y la mesa
 Una vez que hemos agregado el contenido a la fila, podemos terminar la fila usando el`EndRow()` método y luego termine la tabla usando el`EndTable()` método.

```csharp
builder. EndRow();
builder. EndTable();
```

## Paso 9: Guarde el documento modificado
Finalmente, guardamos el documento modificado en un archivo. Puede elegir un nombre y una ubicación apropiados para el documento de salida.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

¡Felicidades! Ahora ha aplicado el formato de fila a una tabla con Aspose.Words para .NET.

### Ejemplo de código fuente para aplicar formato de fila con Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Conclusión
En este tutorial, aprendimos cómo aplicar formato de fila a una tabla usando Aspose.Words para .NET. Al seguir esta guía paso a paso, puede integrar fácilmente esta funcionalidad en sus proyectos de C#. La manipulación del formato de las filas de las tablas es un aspecto esencial del procesamiento de documentos y Aspose.Words ofrece una API potente y flexible para lograrlo. Con este conocimiento, puede mejorar la presentación visual de sus documentos de Word y cumplir requisitos específicos.