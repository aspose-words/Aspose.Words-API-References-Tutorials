---
title: Límites del eje
linktitle: Límites del eje
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a establecer los límites de un eje en un gráfico usando Aspose.Words para .NET controlando el rango de valores que se muestran en el eje.
type: docs
weight: 10
url: /es/net/programming-with-charts/bounds-of-axis/
---

Este tutorial explica cómo establecer los límites de un eje en un gráfico usando Aspose.Words para .NET. Al insertar un gráfico, agregar datos de serie y configurar la escala del eje, puede definir los valores mínimo y máximo para el eje.

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

## Paso 3: Insertar y configurar un gráfico
 Inserte un gráfico en el documento usando el`InsertChart` metodo de la`DocumentBuilder` objeto. Establezca el tipo de gráfico y las dimensiones deseadas.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 4: Agregar datos de la serie
Borre cualquier serie existente en el gráfico y agregue nuevos datos de serie. En este ejemplo, agregamos una serie con las etiquetas "Artículo 1" a "Artículo 5" y los valores correspondientes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Paso 5: establecer los límites del eje
 Configure la escala del eje Y configurando los valores mínimo y máximo usando el`Scaling.Minimum` y`Scaling.Maximum` propiedades del eje.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Paso 6: Guarde el documento
 Guarde el documento en el directorio especificado usando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Ejemplo de código fuente para Bounds Of Axis usando Aspose.Words para .NET 

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
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

¡Eso es todo! Ha establecido correctamente los límites de un eje en un gráfico utilizando Aspose.Words para .NET.