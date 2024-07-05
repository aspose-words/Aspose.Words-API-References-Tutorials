---
title: Crear y personalizar gráficos usando formas
linktitle: Crear y personalizar gráficos usando formas
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear y personalizar un gráfico usando una forma en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/create-chart-using-shape/
---

Este tutorial explica cómo crear un gráfico usando una forma en un documento de Word usando Aspose.Words para .NET.

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
 Crear una nueva instancia del`Document` clase y un`DocumentBuilder`objeto de trabajar con el documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: insertar y configurar una forma de gráfico
 Inserte una forma de gráfico en el documento usando el`InsertChart` método de la`DocumentBuilder` objeto. Establezca el tipo de gráfico y las dimensiones que desee.

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

## Paso 5: guarde el documento
 Guarde el documento en el directorio especificado utilizando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithCharts.CreateChartUsingShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Código fuente de ejemplo para crear un gráfico usando formas usando Aspose.Words para .NET 

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
	// Tenga en cuenta que si se especifica un valor nulo o vacío como texto del título, se mostrará el título generado automáticamente.
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

¡Eso es todo! Ha creado con éxito un gráfico utilizando una forma en un documento de Word utilizando Aspose.Words para .NET.

## Conclusión
En este tutorial, aprendió cómo crear un gráfico usando una forma en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso, puede insertar y configurar una forma de gráfico, personalizar su apariencia y guardar el documento. Aspose.Words para .NET proporciona un conjunto completo de funciones para el procesamiento de textos con documentos y gráficos de Word, lo que le permite crear gráficos de aspecto profesional y visualmente atractivos directamente en sus aplicaciones .NET.

### Preguntas frecuentes

#### P1. ¿Puedo crear gráficos en un documento de Word usando Aspose.Words para .NET?
Sí, con Aspose.Words para .NET, puede crear gráficos en un documento de Word mediante programación. Aspose.Words proporciona API y funcionalidades para insertar varios tipos de gráficos, personalizar su apariencia y manipular datos de gráficos.

#### P2. ¿Qué tipos de gráficos son compatibles con Aspose.Words para .NET?
Aspose.Words para .NET admite una amplia gama de tipos de gráficos, incluidos gráficos de líneas, gráficos de barras, gráficos circulares, gráficos de áreas, gráficos de dispersión y más. Puede elegir el tipo de gráfico apropiado según sus datos y requisitos de visualización.

#### P3. ¿Puedo personalizar la apariencia del gráfico creado?
Sí, puede personalizar la apariencia del gráfico creado utilizando Aspose.Words para .NET. Puede modificar propiedades como el título del gráfico, la posición de la leyenda, las etiquetas de datos, las etiquetas de los ejes, los colores y otros elementos visuales para satisfacer sus necesidades específicas de diseño y formato.
