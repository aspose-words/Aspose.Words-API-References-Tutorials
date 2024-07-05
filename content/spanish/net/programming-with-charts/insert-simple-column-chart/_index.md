---
title: Insertar gráfico de columnas simple en un documento de Word
linktitle: Insertar gráfico de columnas simple en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar un gráfico de columnas simple en un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/insert-simple-column-chart/
---

Este tutorial explica cómo usar Aspose.Words para .NET para insertar un gráfico de columnas simple en un documento. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y guardar el documento.

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

 A continuación, utilice el`InsertChart` método de la`DocumentBuilder` para insertar un gráfico de columnas en el documento. Puede especificar diferentes tipos y tamaños de gráficos según sus requisitos.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: agregar datos de la serie al gráfico

Agregue datos de series al gráfico. En este ejemplo, agregaremos varias series con dos categorías cada una.

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## Paso 4: guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` método de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

Esto completa la implementación de insertar un gráfico de columnas simple usando Aspose.Words para .NET.

### Código fuente de ejemplo para Insertar gráfico de columnas simple usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Puede especificar diferentes tipos y tamaños de gráficos.
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	// Eliminar series generadas por defecto.
	seriesColl.Clear();
	// Cree una matriz de nombres de categorías, en este tutorial tenemos dos categorías.
	string[] categories = new string[] { "Category 1", "Category 2" };
	// Tenga en cuenta que las matrices de datos no deben estar vacías y deben tener el mismo tamaño.
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Conclusión

En este tutorial, ha aprendido cómo insertar un gráfico de columnas simple en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, puede crear un nuevo documento, insertar un gráfico de columnas, agregar varias series con categorías y valores correspondientes y guardar el documento con el gráfico.

Aspose.Words para .NET proporciona una API potente y flexible para el procesamiento de textos con gráficos en documentos de Word. El gráfico de columnas simple es una forma eficaz de representar y comparar datos en diferentes categorías. Con Aspose.Words para .NET, puede crear fácilmente gráficos de columnas con datos personalizados, agregar varias series para realizar comparaciones visuales y personalizar la apariencia del gráfico según sus requisitos.

Al utilizar Aspose.Words para .NET, puede automatizar el proceso de generación de documentos con gráficos de columnas, ahorrando tiempo y esfuerzo en la creación manual de documentos. La biblioteca ofrece una amplia gama de tipos de gráficos, incluidos gráficos de columnas simples, y proporciona varias opciones de personalización para adaptar la apariencia del gráfico a sus necesidades.

### Preguntas frecuentes

#### P1. ¿Qué es un gráfico de columnas?
Un gráfico de columnas es un tipo de gráfico que muestra datos mediante barras verticales de diferentes alturas. Cada columna representa una categoría y la altura de la columna corresponde al valor de esa categoría. Los gráficos de columnas se utilizan comúnmente para comparar datos entre diferentes categorías o para realizar un seguimiento de los cambios a lo largo del tiempo.

#### P2. ¿Puedo agregar varias series al gráfico de columnas?
Sí, al usar Aspose.Words para .NET, puede agregar varias series al gráfico de columnas. Cada serie representa un conjunto de puntos de datos con sus respectivas categorías y valores. Al agregar varias series, puede comparar y analizar diferentes conjuntos de datos dentro del mismo gráfico de columnas, lo que brinda una vista completa de sus datos.

#### P3. ¿Puedo personalizar la apariencia del gráfico de columnas?
Sí, Aspose.Words para .NET le permite personalizar varios aspectos de la apariencia del gráfico de columnas. Puede modificar propiedades como el color de la serie, las etiquetas de los ejes, las etiquetas de datos y el formato del área del gráfico. La biblioteca proporciona un amplio conjunto de API para controlar los elementos visuales del gráfico y crear una apariencia personalizada que se adapte a sus necesidades.

#### P4. ¿Puedo guardar el documento con el gráfico de columnas insertado en diferentes formatos?
 Sí, Aspose.Words para .NET le permite guardar el documento con el gráfico de columnas insertado en varios formatos, como DOCX, PDF, HTML y más. Puede elegir el formato de salida deseado según sus requisitos y utilizar el`Save` método de la`Document` objeto para guardar el documento. El gráfico de columnas insertado se conservará en el documento guardado.

#### P5. ¿Puedo modificar los datos y la apariencia del gráfico de columnas después de insertarlo?
Sí, después de insertar el gráfico de columnas en el documento, puede modificar sus datos y su apariencia utilizando las API proporcionadas por Aspose.Words para .NET. Puede actualizar los datos de la serie con nuevas categorías y valores, cambiar los colores y el formato de las columnas, personalizar las propiedades de los ejes y aplicar varias opciones de formato para crear gráficos dinámicos y visualmente atractivos en sus documentos de Word.