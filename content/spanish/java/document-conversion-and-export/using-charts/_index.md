---
title: Uso de gráficos en Aspose.Words para Java
linktitle: Usando gráficos
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a crear y personalizar gráficos en Aspose.Words para Java. Explore tipos de gráficos, formatos y propiedades de ejes para la visualización de datos.
type: docs
weight: 12
url: /es/java/document-conversion-and-export/using-charts/
---

## Introducción al uso de gráficos en Aspose.Words para Java

En este tutorial, exploraremos cómo trabajar con gráficos usando Aspose.Words para Java. Aprenderá a crear varios tipos de gráficos, personalizar las propiedades de los ejes, dar formato a etiquetas de datos y más. ¡Vamos a sumergirnos!

## Crear un gráfico de líneas

Para crear un gráfico de líneas, utilice el siguiente código:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.LINE, 432.0, 252.0);
Chart chart = shape.getChart();
chart.getTitle().setText("Data Labels With Different Number Format");

// Eliminar series generadas por defecto.
chart.getSeries().clear();

// Agregar una serie con datos y etiquetas de datos.
ChartSeries series1 = chart.getSeries().add("Aspose Series 1", 
    new String[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });

series1.hasDataLabels(true);
series1.getDataLabels().setShowValue(true);
series1.getDataLabels().get(0).getNumberFormat().setFormatCode("\"$\"#,##0.00");
series1.getDataLabels().get(1).getNumberFormat().setFormatCode("dd/mm/yyyy");
series1.getDataLabels().get(2).getNumberFormat().setFormatCode("0.00%");

// O vincular el código de formato a una celda de origen.
series1.getDataLabels().get(2).getNumberFormat().isLinkedToSource(true);

doc.save("Your Directory Path" + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Crear otros tipos de gráficos

Puede crear diferentes tipos de gráficos, como columnas, áreas, burbujas, dispersión y más, utilizando técnicas similares. A continuación se muestra un ejemplo de cómo insertar un gráfico de columnas simple:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// Eliminar series generadas por defecto.
chart.getSeries().clear();

// Creando categorías y agregando datos.
String[] categories = new String[] { "Category 1", "Category 2" };
chart.getSeries().add("Aspose Series 1", categories, new double[] { 1.0, 2.0 });
chart.getSeries().add("Aspose Series 2", categories, new double[] { 3.0, 4.0 });

doc.save("Your Directory Path" + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Personalización de las propiedades del eje

Puede personalizar las propiedades del eje, como cambiar el tipo de eje, configurar marcas, formatear etiquetas y más. A continuación se muestra un ejemplo de cómo definir las propiedades del eje XY:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.AREA, 432.0, 252.0);
Chart chart = shape.getChart();

// Borre la serie predeterminada y agregue sus datos.

ChartAxis xAxis = chart.getAxisX();
ChartAxis yAxis = chart.getAxisY();

// Cambie el eje X para que sea una categoría en lugar de una fecha.
xAxis.setCategoryType(AxisCategoryType.CATEGORY);
xAxis.setCrosses(AxisCrosses.CUSTOM);
xAxis.setCrossesAt(3.0); //Medido en unidades de visualización del eje Y (centenares).
xAxis.setReverseOrder(true);
xAxis.setMajorTickMark(AxisTickMark.CROSS);
xAxis.setMinorTickMark(AxisTickMark.OUTSIDE);
xAxis.setTickLabelOffset(200);

yAxis.setTickLabelPosition(AxisTickLabelPosition.HIGH);
yAxis.setMajorUnit(100.0);
yAxis.setMinorUnit(50.0);
yAxis.getDisplayUnit().setUnit(AxisBuiltInUnit.HUNDREDS);
yAxis.getScaling().setMinimum(new AxisBound(100.0));
yAxis.getScaling().setMaximum(new AxisBound(700.0));

doc.save("Your Directory Path" + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Formatear etiquetas de datos

Puede formatear etiquetas de datos con diferentes formatos numéricos. He aquí un ejemplo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// Borre la serie predeterminada y agregue sus datos.

chart.getAxisY().getNumberFormat().setFormatCode("#,##0");

doc.save("Your Directory Path" + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Personalizaciones de gráficos adicionales

Puede personalizar aún más sus gráficos ajustando límites, unidades de intervalo entre etiquetas, ocultando ejes de gráficos y más. Explore los fragmentos de código proporcionados para obtener más información sobre estas opciones.

## Conclusión

En este tutorial, exploramos cómo trabajar con gráficos usando Aspose.Words para Java. Ha aprendido a crear varios tipos de gráficos, personalizar las propiedades de los ejes, dar formato a las etiquetas de datos y más. Aspose.Words para Java proporciona poderosas herramientas para agregar representaciones visuales de datos a sus documentos, mejorando la forma en que presenta la información.

## Preguntas frecuentes

### ¿Cómo puedo agregar varias series a un gráfico?

 Puede agregar varias series a un gráfico utilizando el`chart.getSeries().add()` método. Asegúrese de especificar el nombre de la serie, las categorías y los valores de datos.

### ¿Cómo puedo formatear etiquetas de datos con formatos de números personalizados?

Puede formatear etiquetas de datos accediendo al`DataLabels` propiedades de una serie y configurar el código de formato deseado usando`getNumberFormat().setFormatCode()`.

### ¿Cómo personalizo las propiedades de los ejes en un gráfico?

 Puede personalizar las propiedades de los ejes, como el tipo, las marcas de graduación, las etiquetas y más, accediendo a la`ChartAxis` propiedades como`setCategoryType()`, `setCrosses()` , y`setMajorTickMark()`.

### ¿Cómo puedo crear otros tipos de gráficos como gráficos de dispersión o de áreas?

 Puede crear varios tipos de gráficos especificando el apropiado`ChartType` al insertar el gráfico usando`builder.insertChart(ChartType.TYPE, width, height)`.

### ¿Cómo puedo ocultar un eje de gráfico?

 Puede ocultar un eje de gráfico configurando el`setHidden(true)` propiedad del eje.