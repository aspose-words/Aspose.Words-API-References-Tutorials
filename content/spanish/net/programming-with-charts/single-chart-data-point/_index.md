---
title: Personalice un único punto de datos de un gráfico en un gráfico
linktitle: Personalice un único punto de datos de un gráfico en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a personalizar un único punto de datos en un gráfico usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/single-chart-data-point/
---

Este tutorial explica cómo usar Aspose.Words para .NET para personalizar un único punto de datos en un gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, acceder a puntos de datos específicos y modificar sus propiedades.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo utilizando el administrador de paquetes NuGet para instalarlo.
- Una ruta del directorio de documentos donde se guardará el documento de salida.

## Paso 2: cree un nuevo documento e inserte un gráfico.

 Crear un nuevo`Document` objeto y un`DocumentBuilder` para construir el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A continuación, utilice el`InsertChart` método de la`DocumentBuilder` para insertar un gráfico de líneas en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: acceda y personalice los puntos de datos

 Para modificar puntos de datos individuales, debe acceder al`ChartDataPointCollection` de la serie y seleccione el punto de datos deseado utilizando el índice.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Paso 4: guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` método de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Esto completa la implementación de la personalización de un único punto de datos en un gráfico usando Aspose.Words para .NET.

### Código fuente de ejemplo para punto de datos de gráfico único usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Conclusión

En este tutorial, aprendió cómo personalizar un único punto de datos en un gráfico usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, puede crear un nuevo documento, insertar un gráfico de líneas, acceder a puntos de datos específicos dentro de la serie de gráficos y modificar sus propiedades para lograr la personalización deseada.

Aspose.Words para .NET proporciona potentes funciones para manipular gráficos en documentos de Word. Al acceder a puntos de datos individuales dentro de una serie de gráficos, puede aplicar modificaciones específicas para personalizar su apariencia y comportamiento. Esto le permite resaltar puntos de datos específicos, cambiar símbolos de marcadores, ajustar tamaños de marcadores y más, para mejorar la representación visual de su gráfico.

La personalización de puntos de datos individuales le brinda la flexibilidad de enfatizar datos importantes o resaltar tendencias específicas en su gráfico. Con Aspose.Words para .NET, puede acceder y modificar fácilmente puntos de datos en varios tipos de gráficos, lo que le permite crear gráficos visualmente atractivos e informativos en sus documentos de Word.

### Preguntas frecuentes

#### P1. ¿Puedo personalizar varios puntos de datos en un gráfico?
 Sí, puede personalizar varios puntos de datos en un gráfico utilizando Aspose.Words para .NET. Al acceder al`ChartDataPointCollection`de una serie, puede seleccionar y modificar múltiples puntos de datos según sus índices. Utilice un bucle o asignaciones individuales para modificar las propiedades deseadas para cada punto de datos. De esta manera, puede aplicar diferentes personalizaciones a múltiples puntos de datos dentro del mismo gráfico.

#### P2. ¿Cómo puedo cambiar el símbolo del marcador de un punto de datos?
 Para cambiar el símbolo de marcador de un punto de datos en un gráfico usando Aspose.Words para .NET, debe acceder al`Marker` propiedad de la`ChartDataPoint` objeto y establecer el`Symbol` propiedad al símbolo de marcador deseado. Los símbolos de marcador representan la forma o icono utilizado para representar cada punto de datos en el gráfico. Puede elegir entre una variedad de símbolos de marcador integrados, como círculo, cuadrado, diamante, triángulo, estrella y más.

#### P3. ¿Puedo ajustar el tamaño de un marcador de punto de datos?
 Sí, puede ajustar el tamaño de un marcador de punto de datos en un gráfico usando Aspose.Words para .NET. Acceder al`Marker` propiedad de la`ChartDataPoint` objeto y establecer el`Size`propiedad al tamaño de marcador deseado. El tamaño del marcador normalmente se especifica en puntos, donde un valor mayor representa un tamaño de marcador mayor. Ajustar el tamaño del marcador le permite enfatizar puntos de datos específicos o diferenciarlos según su importancia.

#### P4. ¿Qué otras propiedades puedo modificar para un punto de datos?
Aspose.Words para .NET proporciona una variedad de propiedades que puede modificar para un punto de datos en un gráfico. Algunas de las propiedades comúnmente modificadas incluyen el símbolo del marcador, el tamaño del marcador, el color del marcador, la visibilidad de la etiqueta de datos, la explosión, invertir si es negativo y más. Estas propiedades le permiten personalizar la apariencia, el comportamiento y la interactividad de puntos de datos individuales, lo que le permite crear gráficos adaptados a sus requisitos específicos.

#### P5. ¿Puedo personalizar puntos de datos en otros tipos de gráficos?
Sí, puede personalizar puntos de datos en varios tipos de gráficos utilizando Aspose.Words para .NET. Si bien este tutorial muestra la personalización de puntos de datos en un gráfico de líneas, puede aplicar técnicas similares a otros tipos de gráficos, como gráficos de columnas, gráficos de barras, gráficos circulares y más. El proceso implica acceder a las series y puntos de datos dentro del gráfico y modificar sus propiedades en consecuencia.