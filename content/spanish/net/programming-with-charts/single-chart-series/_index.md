---
title: Personalizar series de gráficos únicos en un gráfico
linktitle: Personalizar series de gráficos únicos en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a personalizar series de gráficos individuales en un gráfico usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/single-chart-series/
---

Este tutorial explica cómo usar Aspose.Words para .NET para personalizar series de gráficos individuales en un gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, acceder a series específicas y modificar sus propiedades.

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

 A continuación, utilice el`InsertChart` método de la`DocumentBuilder` para insertar un gráfico de líneas en el documento.

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

## Paso 4: guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` método de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

Esto completa la implementación de la personalización de una única serie de gráficos utilizando Aspose.Words para .NET.

### Código fuente de ejemplo para Single Chart Series usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	// También puede especificar si la línea que conecta los puntos del gráfico se suavizará utilizando splines de Catmull-Rom.
	series0.Smooth = true;
	series1.Smooth = true;
	// Especifica si, de forma predeterminada, el elemento principal invertirá sus colores si el valor es negativo.
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Conclusión

En este tutorial, ha aprendido cómo personalizar una única serie de gráficos en un gráfico utilizando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, puede crear un nuevo documento, insertar un gráfico de líneas, acceder a series de gráficos específicas y modificar sus propiedades para lograr la personalización deseada.

Aspose.Words para .NET proporciona potentes funciones para manipular gráficos en documentos de Word. Al acceder a series de gráficos individuales, puede aplicar modificaciones específicas para personalizar su apariencia y comportamiento. Esto le permite cambiar el nombre de la serie, habilitar el suavizado de la línea del gráfico, personalizar marcadores para puntos de datos, invertir colores para valores negativos y más, para mejorar la representación visual de su gráfico.

Personalizar una única serie de gráficos le brinda la flexibilidad de resaltar datos específicos o enfatizar tendencias particulares dentro de su gráfico. Con Aspose.Words para .NET, puede acceder y modificar fácilmente las propiedades de las series de gráficos, lo que le permite crear gráficos visualmente atractivos e informativos en sus documentos de Word.

### Preguntas frecuentes

#### P1. ¿Puedo personalizar varias series de gráficos en un gráfico?
 Sí, puede personalizar varias series de gráficos en un gráfico utilizando Aspose.Words para .NET. Al acceder al`ChartSeries`objetos dentro del gráfico, puede seleccionar y modificar múltiples series según sus índices o criterios específicos. Utilice un bucle o asignaciones individuales para modificar las propiedades deseadas para cada serie de gráficos. De esta manera, puede aplicar diferentes personalizaciones a varias series dentro del mismo gráfico.

#### P2. ¿Cómo puedo cambiar el nombre de una serie de gráficos?
 Para cambiar el nombre de una serie de gráficos en un gráfico usando Aspose.Words para .NET, debe acceder a`Name` propiedad de la`ChartSeries` objeto y configúrelo con el nombre deseado. El nombre de la serie normalmente se muestra en la leyenda del gráfico o en las etiquetas de datos, lo que proporciona una etiqueta descriptiva para la serie. Al modificar el nombre de la serie, puede proporcionar nombres significativos que reflejen los datos representados por cada serie.

#### P3. ¿Qué es el suavizado de series de gráficos?
El suavizado de series de gráficos es una técnica de mejora visual que le permite crear una línea suave que conecta los puntos del gráfico. Aplica un algoritmo de suavizado, como las splines de Catmull-Rom, para interpolar entre puntos de datos y crear una curva visualmente agradable. Para habilitar el suavizado de series en un gráfico usando Aspose.Words para .NET, acceda al`Smooth` propiedad de la`ChartSeries` objeto y configúrelo en`true`. El suavizado puede resultar útil para mostrar tendencias o patrones en datos con fluctuaciones irregulares.

#### P4. ¿Cómo puedo personalizar marcadores para puntos de datos en una serie de gráficos?
 Para personalizar marcadores para puntos de datos en una serie de gráficos usando Aspose.Words para .NET, debe acceder al`Marker` propiedad de la`ChartSeries` objeto y modificar sus propiedades como`Symbol` y`Size`. Los marcadores son indicadores visuales colocados en el gráfico para representar puntos de datos individuales. Puede elegir entre una variedad de símbolos de marcadores integrados y ajustar su tamaño para resaltar o diferenciar puntos de datos específicos dentro de la serie.

#### P5. ¿Puedo invertir colores para valores negativos en una serie de gráficos?
 Sí, puede invertir colores para valores negativos en una serie de gráficos usando Aspose.Words para .NET. Al configurar el`InvertIfNegative` propiedad de la`ChartSeries` oponerse a`true`, los colores de los puntos de datos con valores negativos se invertirán, haciéndolos visualmente distintos de los valores positivos. Esta característica puede resultar útil al comparar valores positivos y negativos en una serie de gráficos, proporcionando una clara diferenciación entre los dos.