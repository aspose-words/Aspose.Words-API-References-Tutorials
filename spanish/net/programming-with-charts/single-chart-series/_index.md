---
title: Serie de un solo gráfico
linktitle: Serie de un solo gráfico
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a personalizar series de gráficos individuales en un gráfico con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/single-chart-series/
---

Este tutorial explica cómo usar Aspose.Words para .NET para personalizar series de gráficos individuales en un gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, acceder a series específicas y modificar sus propiedades.

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

 A continuación, utilice el`InsertChart` metodo de la`DocumentBuilder` para insertar un gráfico de líneas en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: acceda y personalice series de gráficos

 Para modificar series de gráficos individuales, debe acceder a la`ChartSeries` objetos del gráfico.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Paso 4: Guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Esto completa la implementación de la personalización de una sola serie de gráficos mediante Aspose.Words para .NET.

### Ejemplo de código fuente para Single Chart Series usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// También puede especificar si la línea que conecta los puntos en el gráfico se suavizará utilizando splines de Catmull-Rom.
	series0.Smooth = true;
	series1.Smooth = true;
	// Especifica si por defecto el elemento padre invertirá sus colores si el valor es negativo.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```