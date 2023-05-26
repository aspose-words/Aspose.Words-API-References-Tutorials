---
title: Definir las propiedades del eje XYA
linktitle: Definir las propiedades del eje XYA
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a definir las propiedades del eje XY en un gráfico con Aspose.Words para .NET. Se muestran las opciones de personalización para los ejes X e Y.
type: docs
weight: 10
url: /es/net/programming-with-charts/define-xyaxis-properties/
---

Este tutorial explica cómo usar Aspose.Words para .NET para definir las propiedades de los ejes X e Y en un gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de serie y personalizar las propiedades del eje.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo del sitio web oficial de Aspose o usar el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio del documento donde se guardará el documento de salida.

## Paso 2: Cree un nuevo documento e inserte un gráfico

 Crear un nuevo`Document` objeto y un`DocumentBuilder` para construir el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A continuación, inserte un gráfico en el documento utilizando el`InsertChart` metodo de la`DocumentBuilder`. En este ejemplo, insertaremos un gráfico de áreas.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: Agregar datos de series al gráfico

Agregue datos de serie al gráfico. En este ejemplo, agregaremos cinco puntos de datos con fechas y valores correspondientes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## Paso 4: personalizar las propiedades de los ejes X e Y

 Para personalizar las propiedades de los ejes X e Y, acceda a la`ChartAxis` objetos asociados con el gráfico.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Modificar las propiedades de la`xAxis` y`yAxis`objetos para establecer las opciones deseadas para los ejes X e Y. En este ejemplo, demostraremos algunas propiedades comunes que se pueden personalizar.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Paso 5: Guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Esto completa la implementación de la definición de las propiedades del eje XY en un gráfico usando Aspose.Words para .NET.

### Código fuente de ejemplo para Definir propiedades XYAxis usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insertar gráfico
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Cambie el eje X para que sea categoría en lugar de fecha, de modo que todos los puntos se coloquen con el mismo intervalo en el eje X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; // Medido en unidades de visualización del eje Y (centenas).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```