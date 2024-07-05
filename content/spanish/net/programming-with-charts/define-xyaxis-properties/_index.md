---
title: Definir las propiedades del eje XY en un gráfico
linktitle: Definir las propiedades del eje XY en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a definir las propiedades del eje XY en un gráfico usando Aspose.Words para .NET. Se demuestran las opciones de personalización para los ejes X e Y.
type: docs
weight: 10
url: /es/net/programming-with-charts/define-xyaxis-properties/
---

Este tutorial explica cómo usar Aspose.Words para .NET para definir propiedades para los ejes X e Y en un gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y personalizar las propiedades del eje.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo utilizando el administrador de paquetes NuGet para instalarlo.
- Una ruta del directorio de documentos donde se guardará el documento de salida.

## Paso 2: cree un nuevo documento e inserte un gráfico

 Crear un nuevo`Document` objeto y un`DocumentBuilder` para construir el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A continuación, inserte un gráfico en el documento utilizando el`InsertChart` método de la`DocumentBuilder`. En este ejemplo, insertaremos un gráfico de áreas.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: agregar datos de la serie al gráfico

Agregue datos de series al gráfico. En este ejemplo, agregaremos cinco puntos de datos con fechas y valores correspondientes.

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

## Paso 4: Personaliza las propiedades de los ejes X e Y

 Para personalizar las propiedades de los ejes X e Y, acceda al`ChartAxis` objetos asociados con el gráfico.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Modificar las propiedades del`xAxis` y`yAxis`objetos para establecer las opciones deseadas para los ejes X e Y. En este ejemplo, demostraremos algunas propiedades comunes que se pueden personalizar.

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

## Paso 5: guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` método de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Esto completa la implementación de la definición de propiedades del eje XY en un gráfico usando Aspose.Words para .NET.

### Código fuente de ejemplo para definir propiedades de XYAxis usando Aspose.Words para .NET 

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
	xAxis.CrossesAt = 3; //Medido en unidades de visualización del eje Y (centenares).
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

## Conclusión

En este tutorial, aprendió cómo definir propiedades para los ejes X e Y en un gráfico usando Aspose.Words para .NET. Siguiendo la guía paso a paso, puede crear un gráfico, agregar datos de series y personalizar las propiedades del eje para cumplir con sus requisitos específicos. Aspose.Words para .NET proporciona una API integral para el procesamiento de palabras con gráficos en documentos de Word, lo que le permite manipular varios aspectos del gráfico, incluidos los ejes.

Al acceder al`ChartAxis` objetos asociados con el gráfico, puede modificar propiedades como el tipo de categoría, cruces de ejes, marcas de graduación, posiciones de etiquetas, escala y más. Esta flexibilidad le permite personalizar la apariencia y el comportamiento de los ejes del gráfico para presentar sus datos de manera efectiva.

Al utilizar Aspose.Words para .NET, puede integrar perfectamente las capacidades de personalización y creación de gráficos en sus aplicaciones .NET y automatizar la generación de documentos de aspecto profesional con visualizaciones enriquecidas.

### Preguntas frecuentes

#### P1. ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una potente biblioteca de procesamiento de documentos que permite a los desarrolladores crear, manipular y guardar documentos de Word mediante programación en aplicaciones .NET. Proporciona una amplia gama de funciones para el procesamiento de textos con elementos de documentos, incluidos gráficos.

#### P2. ¿Cómo puedo instalar Aspose.Words para .NET?
Puede instalar Aspose.Words para .NET descargándolo mediante el administrador de paquetes NuGet en Visual Studio. Simplemente busque "Aspose.Words" en el administrador de paquetes NuGet e instálelo en su proyecto.

#### P3. ¿Puedo personalizar otros aspectos del gráfico usando Aspose.Words para .NET?
Sí, Aspose.Words para .NET proporciona amplias capacidades para personalizar varios aspectos de un gráfico. Además de definir las propiedades de los ejes, puede modificar el tipo de gráfico, la serie de datos, la leyenda, el título, el área del gráfico, las etiquetas de datos y muchos otros elementos del gráfico. La API ofrece un control detallado sobre la apariencia y el comportamiento de los gráficos.

#### P4. ¿Puedo crear diferentes tipos de gráficos usando Aspose.Words para .NET?
 Sí, Aspose.Words para .NET admite una amplia gama de tipos de gráficos, incluidos área, barras, líneas, circulares, de dispersión y más. Puedes usar el`ChartType` enumeración para especificar el tipo de gráfico deseado al insertar una forma de gráfico en un documento de Word.

#### P5. ¿Puedo guardar el gráfico en diferentes formatos?
Sí, Aspose.Words para .NET le permite guardar el documento que contiene el gráfico en varios formatos, como DOCX, PDF, HTML y más. Puede elegir el formato apropiado según sus requisitos y utilizar el`Save` método de la`Document` objeto para guardar el documento.

#### P6. ¿Puedo aplicar estas técnicas a varios gráficos en un documento?
 Sí, puede aplicar estas técnicas a varios gráficos en un documento repitiendo los pasos necesarios para cada gráfico. Puedes crear separados`Chart` y`ChartAxis` objetos para cada gráfico y personalizar sus propiedades en consecuencia. Aspose.Words para .NET brinda soporte completo para el procesamiento de palabras con múltiples gráficos en un solo documento.