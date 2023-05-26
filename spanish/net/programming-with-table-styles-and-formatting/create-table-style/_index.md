---
title: Crear estilo de tabla
linktitle: Crear estilo de tabla
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para crear un estilo de tabla personalizado con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/create-table-style/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para crear un estilo de tabla usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo crear un estilo personalizado para sus tablas en sus documentos de Word utilizando Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento de Word editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta apropiada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cree un nuevo documento y un generador de documentos
 A continuación, debe crear una nueva instancia de la`Document` clase y un constructor de documentos para ese documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Comience una nueva tabla y agregue celdas
Para comenzar a crear la tabla, usamos el`StartTable()` método del generador de documentos, luego agregamos celdas a la tabla usando el`InsertCell()` y escribimos el contenido de las celdas en el usando el`Write()` método.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Paso 4: crea un estilo de tabla
 Ahora podemos crear un estilo de tabla usando el`TableStyle` clase y el`Add()` método del documento`s `Colección de estilos. Definimos las propiedades del estilo, como bordes, márgenes y rellenos.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Paso 5: aplique el estilo de tabla a la tabla
 Finalmente, aplicamos el estilo de tabla que creamos a la tabla usando el`Style` propiedad de la tabla.

```csharp
table.Style = tableStyle;
```

## Paso 6: Guarde el documento modificado
Finalmente guarde el documento modificado en un archivo. Puede elegir un nombre y una ubicación apropiados para el documento de salida.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

¡Felicidades! Ahora ha creado un estilo personalizado para su tabla usando Aspose.Words para .NET.

### Ejemplo de código fuente para Crear estilo de tabla usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Conclusión
En este tutorial, aprendimos a crear un estilo de tabla con Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede personalizar fácilmente el estilo de sus tablas en sus documentos de Word. Aspose.Words ofrece una API poderosa y flexible para manipular y formatear tablas en sus documentos. Con este conocimiento, puede mejorar la presentación visual de sus documentos de Word y satisfacer necesidades específicas.