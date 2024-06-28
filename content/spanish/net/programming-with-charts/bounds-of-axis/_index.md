---
title: Límites del eje en un gráfico
linktitle: Límites del eje en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a establecer los límites de un eje en un gráfico usando Aspose.Words para .NET controlando el rango de valores que se muestran en el eje.
type: docs
weight: 10
url: /es/net/programming-with-charts/bounds-of-axis/
---

Este tutorial explica cómo establecer los límites de un eje en un gráfico usando Aspose.Words para .NET. Al insertar un gráfico, agregar datos de series y configurar la escala del eje, puede definir los valores mínimo y máximo para el eje.

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 4: agregar datos de la serie
Borre cualquier serie existente en el gráfico y agregue datos de nuevas series. En este ejemplo, agregamos una serie con etiquetas "Elemento 1" a "Elemento 5" y los valores correspondientes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Paso 5: establecer los límites del eje
 Configure la escala del eje Y estableciendo los valores mínimo y máximo usando el`Scaling.Minimum` y`Scaling.Maximum` propiedades del eje.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Paso 6: guarde el documento
 Guarde el documento en el directorio especificado utilizando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Código fuente de ejemplo para Bounds Of Axis usando Aspose.Words para .NET 

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

¡Eso es todo! Ha establecido con éxito los límites de un eje en un gráfico utilizando Aspose.Words para .NET.

## Conclusión
En este tutorial, aprendió cómo establecer los límites de un eje en un gráfico usando Aspose.Words para .NET. Siguiendo la guía paso a paso, puede insertar y configurar un gráfico, agregar datos de series y definir los valores mínimo y máximo para la escala del eje. Aspose.Words para .NET proporciona una API potente y flexible para el procesamiento de textos con documentos de Word, lo que le permite crear gráficos dinámicos y visualmente atractivos con facilidad.


### Preguntas frecuentes

#### P1. ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una biblioteca que permite a los desarrolladores trabajar con documentos de Word mediante programación. Proporciona una amplia gama de características y funcionalidades para crear, manipular y guardar documentos de Word.

#### P2. ¿Cómo puedo instalar Aspose.Words para .NET?
Para instalar Aspose.Words para .NET, puede utilizar el administrador de paquetes NuGet en Visual Studio. Simplemente busque "Apose.Words" en el administrador de paquetes NuGet e instálelo en su proyecto.

#### P3. ¿Puedo utilizar Aspose.Words para .NET con otros lenguajes de programación?
No, Aspose.Words para .NET está diseñado específicamente para aplicaciones .NET. Funciona con lenguajes de programación como C# y VB.NET.

#### P4. ¿Existen otros requisitos previos para utilizar Aspose.Words para .NET?
Además de instalar la biblioteca Aspose.Words para .NET, debe tener conocimientos básicos de programación en C# y procesamiento de textos con documentos de Word. También será útil estar familiarizado con el marco .NET.
