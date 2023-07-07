---
title: Opciones predeterminadas para etiquetas de datos
linktitle: Opciones predeterminadas para etiquetas de datos
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a configurar las opciones predeterminadas para las etiquetas de datos en un gráfico con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/default-options-for-data-labels/
---

Este tutorial explica cómo usar Aspose.Words para .NET para configurar las opciones predeterminadas para las etiquetas de datos en un gráfico. El código proporcionado demuestra cómo crear un gráfico, agregar series de datos y personalizar las etiquetas de datos con Aspose.Words.

## Paso 1: configurar el proyecto

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo del sitio web oficial de Aspose o usar el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio del documento donde se guardará el documento de salida.

## Paso 2: Cree un nuevo documento e inserte un gráfico

 Primero, vamos a crear un nuevo`Document` objeto y un`DocumentBuilder` para construir el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A continuación, insertamos un gráfico en el documento usando el`InsertChart` metodo de la`DocumentBuilder`. En este ejemplo, insertaremos un gráfico circular.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: Agregar series de datos al gráfico

Ahora, agreguemos una serie de datos al gráfico. En este ejemplo, agregaremos tres categorías y sus valores correspondientes.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Paso 4: personaliza las etiquetas de datos

 Para personalizar las etiquetas de datos en el gráfico, necesitamos acceder a la`ChartDataLabelCollection` objeto asociado a la serie.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Entonces podemos modificar varias propiedades del`labels` objeto para establecer las opciones deseadas para las etiquetas de datos. En este ejemplo, habilitaremos la visualización del porcentaje y el valor, deshabilitaremos las líneas guía y estableceremos un separador personalizado.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Paso 5: Guarde el documento

 Finalmente, guardamos el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

Esto completa la implementación de la configuración de opciones predeterminadas para etiquetas de datos en un gráfico usando Aspose.Words para .NET.

### Código fuente de ejemplo para opciones predeterminadas para etiquetas de datos usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```