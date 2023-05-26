---
title: Valores de fecha y hora al eje
linktitle: Valores de fecha y hora al eje
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a agregar valores de fecha y hora al eje de un gráfico usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/date-time-values-to-axis/
---

Este tutorial explica cómo agregar valores de fecha y hora al eje de un gráfico usando Aspose.Words para .NET.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y trabajo con documentos de Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"`con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cree un nuevo documento y DocumentBuilder
 Crear una nueva instancia de la`Document` clase y un`DocumentBuilder` objeto de trabajar con el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Insertar y configurar una forma de gráfico
 Inserte una forma de gráfico en el documento usando el`InsertChart` metodo de la`DocumentBuilder` objeto. Establezca el tipo de gráfico y las dimensiones deseadas.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Paso 4: Agregar datos al gráfico
Agregue datos a la serie de gráficos, incluidos los valores de fecha y hora.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Paso 5: configurar el eje
Configure el eje X del gráfico para mostrar los valores de fecha y hora.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Paso 6: Guarde el documento
 Guarde el documento en el directorio especificado usando el`Save`método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Ejemplo de código fuente para valores de fecha y hora en el eje usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Establezca las unidades principales en una semana y las unidades menores en un día.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Este código de ejemplo crea un nuevo documento de Word, inserta un gráfico de columnas con valores de fecha y hora en el eje X y guarda el documento en el directorio especificado.