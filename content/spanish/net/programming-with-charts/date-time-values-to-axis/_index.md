---
title: Agregar valores de fecha y hora al eje de un gráfico
linktitle: Agregar valores de fecha y hora al eje de un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a agregar valores de fecha y hora al eje de un gráfico usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/date-time-values-to-axis/
---

Este tutorial explica cómo agregar valores de fecha y hora al eje de un gráfico usando Aspose.Words para .NET.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cree un nuevo documento y DocumentBuilder
 Crear una nueva instancia del`Document` clase y un`DocumentBuilder` objeto de trabajar con el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: insertar y configurar una forma de gráfico
 Inserte una forma de gráfico en el documento usando el`InsertChart` método de la`DocumentBuilder` objeto. Establezca el tipo de gráfico y las dimensiones que desee.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Paso 4: agregar datos al gráfico
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

## Paso 6: guarde el documento
 Guarde el documento en el directorio especificado utilizando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Código fuente de ejemplo para valores de fecha y hora al eje usando Aspose.Words para .NET 

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
	// Establezca las unidades mayores en una semana y las unidades menores en un día.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Este código de ejemplo crea un nuevo documento de Word, inserta un gráfico de columnas con valores de fecha y hora en el eje X y guarda el documento en el directorio especificado.

## Conclusión
En este tutorial, aprendió cómo agregar valores de fecha y hora al eje de un gráfico usando Aspose.Words para .NET. Siguiendo la guía paso a paso, puede crear un gráfico, agregar valores de fecha y hora a la serie y configurar el eje para mostrar los valores de fecha y hora con precisión. Aspose.Words para .NET proporciona un poderoso conjunto de funciones para el procesamiento de palabras con gráficos en documentos de Word, lo que le permite representar y visualizar datos con valores de fecha y hora de manera efectiva.

### Preguntas frecuentes

#### P1. ¿Puedo agregar valores de fecha y hora al eje de un gráfico usando Aspose.Words para .NET?
Sí, con Aspose.Words para .NET, puede agregar y mostrar valores de fecha y hora en el eje de un gráfico en un documento de Word. Aspose.Words proporciona API y funcionalidades para trabajar con varios tipos de gráficos y personalizar su apariencia, incluido el manejo de valores de fecha y hora en el eje.

#### P2. ¿Cómo agrego valores de fecha y hora a la serie de gráficos?
 Para agregar valores de fecha y hora a la serie de gráficos, puede utilizar el`Add`método de la serie del gráfico. Proporcione una matriz de valores de fecha y hora como datos de categoría (eje X), junto con los valores de serie correspondientes. Esto le permite trazar puntos de datos con valores de fecha y hora en el gráfico.

#### P3. ¿Cómo puedo configurar el eje para mostrar valores de fecha y hora?
 Puede configurar el eje del gráfico para mostrar valores de fecha y hora configurando las propiedades adecuadas. Por ejemplo, puede especificar los valores mínimo y máximo para el eje utilizando el`Scaling.Minimum` y`Scaling.Maximum` propiedades, respectivamente. Además, puede configurar las unidades mayores y menores para definir el intervalo y las marcas del eje.
