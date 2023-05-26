---
title: Número de formato de la etiqueta de datos
linktitle: Número de formato de la etiqueta de datos
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a formatear la cantidad de etiquetas de datos en un gráfico usando Aspose.Words para .NET. Personalice fácilmente los formatos de números para las etiquetas de datos.
type: docs
weight: 10
url: /es/net/programming-with-charts/format-number-of-data-label/
---

Este tutorial explica cómo usar Aspose.Words para .NET para formatear la cantidad de etiquetas de datos en un gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y personalizar el formato de número de las etiquetas de datos.

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

 A continuación, inserte un gráfico en el documento utilizando el`InsertChart` metodo de la`DocumentBuilder`En este ejemplo, insertaremos un gráfico de líneas.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Paso 3: Agregar datos de series al gráfico

Agregue datos de serie al gráfico. En este ejemplo, agregaremos tres categorías y sus valores correspondientes.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Paso 4: personalice el formato de número de las etiquetas de datos

 Para formatear el número de etiquetas de datos, acceda al`DataLabels` colección asociada a la serie.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

En este ejemplo, configuramos diferentes formatos de números para cada etiqueta de datos. La primera etiqueta de datos tiene formato de moneda, la segunda de fecha y la tercera de porcentaje.

## Paso 5: Guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Esto completa la implementación del formato de la cantidad de etiquetas de datos en un gráfico usando Aspose.Words para .NET.

### Código fuente de ejemplo para número de formato de etiqueta de datos usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Elimina la serie generada por defecto.
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	// O puede configurar el código de formato para que se vincule a una celda de origen,
	// en este caso, NumberFormat se restablecerá a general y se heredará de una celda de origen.
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```