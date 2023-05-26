---
title: Unidad de intervalo entre etiquetas en el eje
linktitle: Unidad de intervalo entre etiquetas en el eje
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a establecer la unidad de intervalo entre etiquetas en el eje de un gráfico usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Este tutorial explica cómo usar Aspose.Words para .NET para establecer la unidad de intervalo entre etiquetas en el eje de un gráfico. El código fuente proporcionado muestra cómo crear un gráfico, agregar datos de series y personalizar las etiquetas de los ejes.

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

 A continuación, utilice el`InsertChart` metodo de la`DocumentBuilder` para insertar un gráfico de columnas en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: Agregar datos de series al gráfico

Agregue datos de serie al gráfico. En este ejemplo, agregaremos cinco elementos con sus valores correspondientes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Paso 4: personaliza las etiquetas de los ejes

 Para establecer la unidad de intervalo entre etiquetas en el eje X, acceda a la`AxisX` propiedad del gráfico y establecer la`TickLabelSpacing` propiedad al valor deseado. En este ejemplo, establecemos el espaciado en 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Paso 5: Guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Esto completa la implementación de establecer la unidad de intervalo entre etiquetas en el eje usando Aspose.Words para .NET.

### Código fuente de ejemplo para Unidad de intervalo entre etiquetas en eje usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```