---
title: Crear gráfico usando forma
linktitle: Crear gráfico usando forma
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear y personalizar un gráfico usando una forma en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/create-chart-using-shape/
---

Este tutorial explica cómo crear un gráfico usando una forma en un documento de Word usando Aspose.Words para .NET.

## requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y trabajo con documentos de Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"`con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cree un nuevo documento y DocumentBuilder
 Crear una nueva instancia de la`Document` clase y un`DocumentBuilder` objeto de trabajar con el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: Insertar y configurar una forma de gráfico
 Inserte una forma de gráfico en el documento usando el`InsertChart` metodo de la`DocumentBuilder` objeto. Establezca el tipo de gráfico y las dimensiones deseadas.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Paso 4: personaliza el gráfico
Personalice el gráfico modificando varias propiedades, como el título y la leyenda del gráfico.

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## Paso 5: Guarde el documento
 Guarde el documento en el directorio especificado usando el`Save`método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Código fuente de ejemplo para Crear gráfico usando Shape usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	// Tenga en cuenta que si se especifica un valor nulo o vacío como texto de título, se mostrará un título generado automáticamente.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

¡Eso es todo! Ha creado correctamente un gráfico usando una forma en un documento de Word usando Aspose.Words para .NET.