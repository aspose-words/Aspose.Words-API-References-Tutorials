---
title: Definir las propiedades del eje XY en un gráfico
linktitle: Definir las propiedades del eje XY en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a definir las propiedades del eje XY en un gráfico usando Aspose.Words para .NET con esta guía paso a paso. Perfecto para desarrolladores .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/define-xyaxis-properties/
---
## Introducción

Los gráficos son una herramienta poderosa para visualizar datos. Cuando necesite crear documentos profesionales con gráficos dinámicos, Aspose.Words para .NET es una biblioteca invaluable. Este artículo lo guiará a través del proceso de definición de las propiedades del eje XY en un gráfico usando Aspose.Words para .NET, desglosando cada paso para garantizar la claridad y facilidad de comprensión.

## Requisitos previos

Antes de sumergirse en la codificación, existen algunos requisitos previos que debe cumplir:

1. Aspose.Words para .NET: asegúrese de tener la biblioteca Aspose.Words para .NET. Puede[descárgalo aquí](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: necesita un entorno de desarrollo integrado (IDE) como Visual Studio.
3. .NET Framework: asegúrese de que su entorno de desarrollo esté configurado para el desarrollo .NET.
4. Conocimientos básicos de C#: esta guía asume que tiene conocimientos básicos de programación en C#.

## Importar espacios de nombres

Para empezar, necesita importar los espacios de nombres necesarios en su proyecto. Esto garantiza que tenga acceso a todas las clases y métodos necesarios para crear y manipular documentos y gráficos.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

Dividiremos el proceso en pasos simples, cada uno de los cuales se centrará en una parte específica de la definición de las propiedades del eje XY en un gráfico.

## Paso 1: Inicialice el documento y DocumentBuilder

 Primero, necesita inicializar un nuevo documento y un`DocumentBuilder` objeto. El`DocumentBuilder` ayuda a insertar contenido en el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: insertar un gráfico

A continuación, insertará un gráfico en el documento. En este ejemplo, usaremos un gráfico de Área. Puede personalizar las dimensiones del gráfico según sea necesario.

```csharp
// Insertar gráfico
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: borre la serie predeterminada y agregue datos personalizados

De forma predeterminada, el gráfico tendrá algunas series predefinidas. Los borraremos y agregaremos nuestra serie de datos personalizados.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
	new DateTime[]
	{
		new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
		new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
	},
	new double[] { 640, 320, 280, 120, 150 });
```

## Paso 4: definir las propiedades del eje X

Ahora es el momento de definir las propiedades para el eje X. Esto incluye configurar el tipo de categoría, personalizar el cruce de ejes y ajustar las marcas y etiquetas.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3; //Medido en unidades de visualización del eje Y (centenares).
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;
```

## Paso 5: definir las propiedades del eje Y

De manera similar, establecerá las propiedades para el eje Y. Esto incluye configurar la posición de la etiqueta de marca, las unidades mayores y menores, la unidad de visualización y la escala.

```csharp
ChartAxis yAxis = chart.AxisY;
yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Paso 6: guarde el documento

Finalmente, guarde el documento en su directorio especificado. Esto generará el documento de Word con el gráfico personalizado.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Conclusión

Crear y personalizar gráficos en documentos de Word usando Aspose.Words para .NET es sencillo una vez que comprende los pasos necesarios. Esta guía lo ha guiado a través del proceso de definir las propiedades del eje XY en un gráfico, desde la inicialización del documento hasta guardar el producto final. Con estas habilidades, podrá crear gráficos detallados y de aspecto profesional que mejoren sus documentos.

## Preguntas frecuentes

### ¿Qué tipos de gráficos puedo crear con Aspose.Words para .NET?
Puede crear varios tipos de gráficos, incluidos áreas, barras, líneas, circulares y más.

### ¿Cómo instalo Aspose.Words para .NET?
 Puede descargar Aspose.Words para .NET desde[aquí](https://releases.aspose.com/words/net/) y siga las instrucciones de instalación proporcionadas.

### ¿Puedo personalizar la apariencia de mis gráficos?
Sí, Aspose.Words para .NET permite una amplia personalización de los gráficos, incluidos colores, fuentes y propiedades de los ejes.

### ¿Hay una prueba gratuita disponible para Aspose.Words para .NET?
 Sí, puedes obtener una prueba gratuita.[aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar más tutoriales y documentación?
 Puede encontrar más tutoriales y documentación detallada en[Página de documentación de Aspose.Words para .NET](https://reference.aspose.com/words/net/).
