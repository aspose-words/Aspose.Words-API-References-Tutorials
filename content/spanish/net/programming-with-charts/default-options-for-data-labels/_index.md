---
title: Establecer opciones predeterminadas para etiquetas de datos en un gráfico
linktitle: Establecer opciones predeterminadas para etiquetas de datos en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar opciones predeterminadas para etiquetas de datos en un gráfico usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/default-options-for-data-labels/
---

Este tutorial explica cómo usar Aspose.Words para .NET para configurar opciones predeterminadas para etiquetas de datos en un gráfico. El código proporcionado demuestra cómo crear un gráfico, agregar series de datos y personalizar las etiquetas de datos usando Aspose.Words.

## Paso 1: configurar el proyecto

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo usando el administrador de paquetes NuGet para instalarlo.
- Una ruta del directorio de documentos donde se guardará el documento de salida.

## Paso 2: cree un nuevo documento e inserte un gráfico

 Primero, creemos un nuevo`Document` objeto y un`DocumentBuilder` para construir el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A continuación, insertamos un gráfico en el documento usando el`InsertChart` método de la`DocumentBuilder`. En este ejemplo, insertaremos un gráfico circular.

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: agregar series de datos al gráfico

Ahora, agreguemos una serie de datos al gráfico. En este ejemplo, agregaremos tres categorías y sus valores correspondientes.

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## Paso 4: personaliza las etiquetas de datos

 Para personalizar las etiquetas de datos en el gráfico, debemos acceder a la`ChartDataLabelCollection` Objeto asociado a la serie.

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

 Luego podemos modificar varias propiedades del`labels`objeto para establecer las opciones deseadas para las etiquetas de datos. En este ejemplo, habilitaremos la visualización del porcentaje y el valor, deshabilitaremos las líneas guía y estableceremos un separador personalizado.

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## Paso 5: guarde el documento

 Finalmente, guardamos el documento en el directorio especificado usando el`Save` método de la`Document` objeto.

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

## Conclusión

En este tutorial, aprendió cómo configurar opciones predeterminadas para etiquetas de datos en un gráfico usando Aspose.Words para .NET. Siguiendo la guía paso a paso, puede crear un gráfico, agregar series de datos y personalizar las etiquetas de datos para cumplir con sus requisitos específicos. Aspose.Words para .NET proporciona una potente API para el procesamiento de palabras con gráficos en documentos de Word, lo que le permite manipular varios elementos de gráficos y lograr la apariencia y funcionalidad deseadas.

 Al establecer las propiedades del`ChartDataLabelCollection`objeto asociado con la serie de gráficos, puede controlar la visualización de etiquetas de datos, incluidas opciones como mostrar porcentajes, valores, líneas guía y separadores personalizados. Esta flexibilidad le permite presentar datos de manera efectiva y mejorar la representación visual de sus gráficos.

### Preguntas frecuentes

#### P1. ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una biblioteca que permite a los desarrolladores crear, manipular y guardar documentos de Word mediante programación utilizando aplicaciones .NET. Proporciona una amplia gama de funciones para el procesamiento de textos con elementos de documentos, incluidos gráficos.

#### P2. ¿Cómo puedo instalar Aspose.Words para .NET?
Puede instalar Aspose.Words para .NET descargándolo mediante el administrador de paquetes NuGet en Visual Studio. Simplemente busque "Aspose.Words" en el administrador de paquetes NuGet e instálelo en su proyecto.

#### P3. ¿Puedo personalizar otros aspectos del gráfico usando Aspose.Words para .NET?
Sí, Aspose.Words para .NET le permite personalizar varios aspectos de un gráfico, como el tipo de gráfico, las etiquetas de los ejes, la leyenda, el área de trazado y más. Puede acceder y modificar diferentes propiedades del objeto del gráfico para lograr la apariencia y el comportamiento deseados.

#### P4. ¿Puedo guardar el gráfico en diferentes formatos?
 Sí, Aspose.Words para .NET admite guardar el documento que contiene el gráfico en varios formatos, incluidos DOCX, PDF, HTML y más. Puede elegir el formato apropiado según sus requisitos y utilizar el`Save` método de la`Document` objeto para guardar el documento.

#### P5. ¿Puedo aplicar estas técnicas a otros tipos de gráficos?
Sí, las técnicas descritas en este tutorial se pueden aplicar a otros tipos de gráficos compatibles con Aspose.Words para .NET. La clave es acceder a los objetos y propiedades relevantes específicos del tipo de gráfico con el que está procesando textos.