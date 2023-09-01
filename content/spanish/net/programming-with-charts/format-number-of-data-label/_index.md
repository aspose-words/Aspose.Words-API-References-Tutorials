---
title: Dar formato al número de etiqueta de datos en un gráfico
linktitle: Dar formato al número de etiqueta de datos en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a formatear la cantidad de etiquetas de datos en un gráfico usando Aspose.Words para .NET. Personalice fácilmente los formatos de números para etiquetas de datos.
type: docs
weight: 10
url: /es/net/programming-with-charts/format-number-of-data-label/
---

Este tutorial explica cómo usar Aspose.Words para .NET para formatear la cantidad de etiquetas de datos en un gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y personalizar el formato numérico de las etiquetas de datos.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo utilizando el administrador de paquetes NuGet para instalarlo.
- Una ruta del directorio de documentos donde se guardará el documento de salida.

## Paso 2: cree un nuevo documento e inserte un gráfico

 Crear un nuevo`Document` objeto y un`DocumentBuilder` para construir el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A continuación, inserte un gráfico en el documento utilizando el`InsertChart` método de la`DocumentBuilder`. En este ejemplo, insertaremos un gráfico de líneas.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## Paso 3: agregar datos de la serie al gráfico

Agregue datos de series al gráfico. En este ejemplo, agregaremos tres categorías y sus valores correspondientes.

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## Paso 4: personaliza el formato numérico de las etiquetas de datos

 Para formatear el número de etiquetas de datos, acceda al`DataLabels` colección asociada a la serie.

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

En este ejemplo, configuramos diferentes formatos de números para cada etiqueta de datos. La primera etiqueta de datos tiene el formato de moneda, la segunda como fecha y la tercera como porcentaje.

## Paso 5: guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` método de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Esto completa la implementación de formatear la cantidad de etiquetas de datos en un gráfico usando Aspose.Words para .NET.

### Código fuente de ejemplo para formatear el número de etiqueta de datos usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	// Eliminar series generadas por defecto.
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

## Conclusión

En este tutorial, aprendió cómo formatear la cantidad de etiquetas de datos en un gráfico usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, puede crear un gráfico, agregar datos de series y personalizar el formato numérico de las etiquetas de datos según sus requisitos.

 Aspose.Words para .NET proporciona una API integral para el procesamiento de palabras con gráficos en documentos de Word, lo que le permite manipular varios aspectos del gráfico, incluidas las etiquetas de datos. Al acceder al`DataLabels` colección asociada con una serie, puede personalizar el formato numérico de las etiquetas de datos individuales.

La API le permite controlar la visualización de valores, establecer diferentes formatos de números para cada etiqueta de datos y vincular el formato de número a una celda de origen. Esta flexibilidad le permite presentar datos numéricos en gráficos con el formato deseado, como símbolos de moneda, formatos de fecha y valores de porcentaje.

Al utilizar Aspose.Words para .NET, puede incorporar poderosas capacidades de gráficos en sus aplicaciones .NET y generar documentos de apariencia profesional con gráficos y etiquetas de datos completamente formateados.

### Preguntas frecuentes

#### P1. ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una biblioteca de procesamiento de documentos rica en funciones que permite a los desarrolladores crear, manipular y guardar documentos de Word mediante programación en aplicaciones .NET. Proporciona una amplia gama de funciones para el procesamiento de textos con elementos de documentos, incluidos gráficos y etiquetas de datos.

#### P2. ¿Cómo puedo instalar Aspose.Words para .NET?
Puede instalar Aspose.Words para .NET descargándolo mediante el administrador de paquetes NuGet en Visual Studio. Simplemente busque "Aspose.Words" en el administrador de paquetes NuGet e instálelo en su proyecto.

#### P3. ¿Puedo formatear otros aspectos del gráfico usando Aspose.Words para .NET?
Sí, Aspose.Words para .NET proporciona amplias capacidades para formatear varios aspectos de un gráfico. Además de las etiquetas de datos, puede personalizar el tipo de gráfico, los datos de la serie, las propiedades de los ejes, la leyenda, el título, el área de trazado y muchos otros elementos del gráfico. La API ofrece un control detallado sobre la apariencia y el formato de los gráficos.

#### P4. ¿Puedo aplicar diferentes formatos de números a diferentes etiquetas de datos en la misma serie?
 Sí, Aspose.Words para .NET le permite aplicar diferentes formatos numéricos a etiquetas de datos individuales dentro de la misma serie. Al acceder al`DataLabels` colección asociada a una serie, puede configurar el`FormatCode` propiedad de cada etiqueta de datos para especificar el formato de número deseado. Esto le permite presentar valores numéricos en diferentes formatos dentro del mismo gráfico.

#### P5. ¿Puedo usar formatos de números personalizados para etiquetas de datos?
 Sí, Aspose.Words para .NET admite formatos de números personalizados para etiquetas de datos. Puede especificar el formato de número deseado configurando el`FormatCode`propiedad de una etiqueta de datos a un código de formato personalizado. Esto le brinda la flexibilidad de aplicar una amplia gama de formatos numéricos, como símbolos de moneda, formatos de fecha, valores de porcentaje y más.

#### P6. ¿Puedo guardar el gráfico con etiquetas de datos formateadas en diferentes formatos?
 Sí, Aspose.Words para .NET le permite guardar el documento que contiene el gráfico con etiquetas de datos formateadas en varios formatos, como DOCX, PDF, HTML y más. Puede elegir el formato apropiado según sus requisitos y utilizar el`Save` método de la`Document` objeto para guardar el documento. Las etiquetas de datos formateadas se conservarán en el documento guardado.