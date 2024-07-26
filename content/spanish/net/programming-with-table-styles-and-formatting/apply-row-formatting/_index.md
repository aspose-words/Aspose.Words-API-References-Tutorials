---
title: Aplicar formato de fila
linktitle: Aplicar formato de fila
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para aplicar formato de fila a una tabla usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

En este tutorial, lo guiaremos paso a paso para aplicar formato de fila a una tabla usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarle a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, comprenderá claramente cómo formatear las filas de una tabla en sus documentos de Word usando Aspose.Words para .NET.

## Paso 1: definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento de Word editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: cree un nuevo documento y un generador de documentos
 A continuación, debe crear una nueva instancia de`Document` clase y un constructor de documentos para ese documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: iniciar un nuevo tablero
 Para aplicar el formato de fila, primero debemos iniciar una nueva tabla usando el`StartTable()` método del constructor del documento.

```csharp
Table table = builder. StartTable();
```

## Paso 4: inserta la celda y ve al formato de fila
Ahora podemos insertar una celda en la tabla y acceder al formato de fila para esa celda usando el generador de documentos.`InsertCell()`y`RowFormat` métodos.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Paso 5: establecer la altura de la fila
 Para establecer la altura de la fila, utilizamos el`Height`y`HeightRule` propiedades del formato de fila. En este ejemplo, establecemos una altura de fila de 100 puntos y usamos el`Exactly` regla.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Paso 6: definir el formato de la tabla
 Algunas propiedades de formato se pueden configurar en la propia tabla y se aplican a todas las filas de la tabla. En este ejemplo, configuramos las propiedades del margen de la tabla usando el`LeftPadding`, `RightPadding`, `TopPadding`y`BottomPadding` propiedades.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Paso 7: agregue contenido a la fila
Ahora podemos

 Agregaremos contenido a la línea usando los métodos del constructor de documentos. En este ejemplo, utilizamos el`Writeln()` Método para agregar texto a la línea.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Paso 8: Termina la línea y la tabla.
 Una vez que hayamos agregado el contenido a la fila, podemos finalizar la fila usando el`EndRow()` método y luego terminar la tabla usando el`EndTable()` método.

```csharp
builder. EndRow();
builder. EndTable();
```

## Paso 9: guarde el documento modificado
Finalmente, guardamos el documento modificado en un archivo. Puede elegir un nombre y una ubicación apropiados para el documento de salida.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

¡Enhorabuena! Ahora ha aplicado formato de fila a una tabla usando Aspose.Words para .NET.

### Código fuente de muestra para aplicar formato de fila usando Aspose.Words para .NET 

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
En este tutorial, aprendimos cómo aplicar formato de fila a una tabla usando Aspose.Words para .NET. Si sigue esta guía paso a paso, podrá integrar fácilmente esta funcionalidad en sus proyectos de C#. La manipulación del formato de las filas de la tabla es un aspecto esencial del procesamiento de documentos y Aspose.Words ofrece una API potente y flexible para lograrlo. Con este conocimiento, podrás mejorar la presentación visual de tus documentos de Word y cumplir con requisitos específicos.