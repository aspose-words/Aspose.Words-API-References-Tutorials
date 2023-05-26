---
title: Ocultar eje de gráfico
linktitle: Ocultar eje de gráfico
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a ocultar el eje del gráfico en un documento con Aspose.Words para .NET. Oculte el eje para una visualización del gráfico más limpia y enfocada.
type: docs
weight: 10
url: /es/net/programming-with-charts/hide-chart-axis/
---

Este tutorial explica cómo usar Aspose.Words para .NET para ocultar el eje del gráfico en un documento. El código fuente proporcionado muestra cómo crear un gráfico, agregar datos de serie y ocultar el eje del gráfico.

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

 A continuación, inserte un gráfico en el documento utilizando el`InsertChart` metodo de la`DocumentBuilder`. En este ejemplo, insertaremos un gráfico de columnas.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: Agregar datos de series al gráfico

Agregue datos de serie al gráfico. En este ejemplo, agregaremos cinco elementos y sus valores correspondientes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Paso 4: ocultar el eje del gráfico

 Para ocultar el eje del gráfico, acceda a la`AxisY` propiedad del gráfico y establecer la`Hidden` propiedad a`true`.

```csharp
chart.AxisY.Hidden = true;
```

En este ejemplo, ocultamos el eje Y del gráfico.

## Paso 5: Guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Esto completa la implementación de ocultar el eje del gráfico usando Aspose.Words para .NET.

### Ejemplo de código fuente para Ocultar eje de gráfico usando Aspose.Words para .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```