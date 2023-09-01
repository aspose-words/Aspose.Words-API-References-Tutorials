---
title: Personalizar la etiqueta de datos del gráfico
linktitle: Personalizar la etiqueta de datos del gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a agregar y personalizar etiquetas de datos en un gráfico usando Aspose.Words para .NET para proporcionar información adicional sobre puntos de datos.
type: docs
weight: 10
url: /es/net/programming-with-charts/chart-data-label/
---

Este tutorial explica cómo agregar y personalizar etiquetas de datos en un gráfico usando Aspose.Words para .NET. Las etiquetas de datos proporcionan información adicional sobre los puntos de datos de un gráfico.

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

## Paso 3: insertar y configurar un gráfico
 Inserte un gráfico en el documento usando el`InsertChart` método de la`DocumentBuilder` objeto. Establezca el tipo de gráfico y las dimensiones que desee.

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## Paso 4: Personaliza las etiquetas de datos
Acceda a la colección de etiquetas de datos de la serie de gráficos y modifique varias propiedades para personalizar la apariencia de las etiquetas de datos.

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## Paso 5: guarde el documento
 Guarde el documento en el directorio especificado utilizando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithCharts.ChartDataLabel.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Código fuente de ejemplo para etiqueta de datos de gráfico usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	// De forma predeterminada, cuando agrega etiquetas de datos a los puntos de datos en un gráfico circular, se muestran líneas guía para las etiquetas de datos que están
	// colocado muy fuera del final de los puntos de datos. Las líneas guía crean una conexión visual entre una etiqueta de datos y su
	// punto de datos correspondiente.
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

¡Eso es todo! Ha agregado y personalizado con éxito etiquetas de datos en un gráfico utilizando Aspose.Words para .NET.

## Conclusión
En este tutorial, aprendió cómo agregar y personalizar etiquetas de datos en un gráfico usando Aspose.Words para .NET. Siguiendo la guía paso a paso, puede insertar un gráfico, acceder a la colección de etiquetas de datos y modificar las propiedades para personalizar la apariencia de las etiquetas de datos. Aspose.Words para .NET proporciona una potente API para el procesamiento de textos con documentos y gráficos de Word, lo que le permite crear gráficos visualmente atractivos e informativos con etiquetas de datos personalizadas.

### Preguntas frecuentes

#### P1. ¿Qué son las etiquetas de datos en un gráfico?
Las etiquetas de datos en un gráfico proporcionan información adicional sobre los puntos de datos representados en el gráfico. Pueden mostrar valores, categorías, nombres de series, porcentajes u otros detalles relevantes según el tipo de gráfico y la configuración.

#### P2. ¿Puedo personalizar la apariencia de las etiquetas de datos?
Sí, puedes personalizar la apariencia de las etiquetas de datos en un gráfico. Aspose.Words para .NET proporciona opciones para modificar varias propiedades de las etiquetas de datos, como mostrar claves de leyenda, líneas guía, nombres de categorías, nombres de series, valores y más. También puede configurar separadores y formatear las etiquetas para cumplir con sus requisitos específicos.

#### P3. ¿Puedo agregar etiquetas de datos a cualquier tipo de gráfico?
Sí, puede agregar etiquetas de datos a varios tipos de gráficos, incluidos gráficos de barras, gráficos circulares, gráficos de líneas y más. El proceso de agregar y personalizar etiquetas de datos puede variar ligeramente según el tipo de gráfico y la biblioteca o herramienta que esté utilizando.
