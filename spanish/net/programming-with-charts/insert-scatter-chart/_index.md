---
title: Insertar gráfico de dispersión en un documento de Word
linktitle: Insertar gráfico de dispersión en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar un gráfico de dispersión en un documento con Aspose.Words para .NET. Agregue datos de series con coordenadas X e Y.
type: docs
weight: 10
url: /es/net/programming-with-charts/insert-scatter-chart/
---

Este tutorial explica cómo usar Aspose.Words para .NET para insertar un gráfico de dispersión en un documento. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y guardar el documento.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo utilizando el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio del documento donde se guardará el documento de salida.

## Paso 2: Cree un nuevo documento e inserte un gráfico

 Crear un nuevo`Document` objeto y un`DocumentBuilder` para construir el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A continuación, utilice el`InsertChart` metodo de la`DocumentBuilder` para insertar un gráfico de dispersión en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: Agregar datos de series al gráfico

Agregue datos de serie al gráfico. En este ejemplo, agregaremos dos conjuntos de coordenadas X e Y.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Paso 4: Guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

Esto completa la implementación de la inserción de un gráfico de dispersión mediante Aspose.Words para .NET.

### Ejemplo de código fuente para Insertar gráfico de dispersión usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Conclusión

En este tutorial, ha aprendido a insertar un gráfico de dispersión en un documento de Word utilizando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente provisto, puede crear un nuevo documento, insertar un gráfico de dispersión, agregar datos de series con coordenadas X e Y y guardar el documento con el gráfico.

Aspose.Words para .NET proporciona una API completa para el procesamiento de textos con gráficos en documentos de Word. Los gráficos de dispersión son útiles para visualizar y analizar datos con dos variables numéricas. Con Aspose.Words para .NET, puede crear fácilmente gráficos de dispersión que representen la relación entre los valores X e Y e identificar patrones o tendencias en los datos.

Al usar Aspose.Words para .NET, puede automatizar el proceso de generación de documentos con gráficos de dispersión, ahorrando tiempo y esfuerzo en la creación manual de documentos. La biblioteca ofrece una amplia gama de tipos de gráficos, incluidos gráficos de dispersión, y proporciona varias opciones de personalización para adaptar la apariencia del gráfico según sus necesidades.

### preguntas frecuentes

#### Q1. ¿Qué es un gráfico de dispersión?
Un gráfico de dispersión es un tipo de gráfico que muestra la relación entre dos variables numéricas. Consiste en una serie de puntos trazados en una cuadrícula de coordenadas, con una variable representada en el eje X y la otra variable representada en el eje Y. Los gráficos de dispersión se utilizan para identificar patrones, correlaciones o tendencias entre dos conjuntos de puntos de datos.

#### Q2. ¿Puedo agregar varias series al gráfico de dispersión?
Sí, puede agregar varias series al gráfico de dispersión mediante Aspose.Words para .NET. Cada serie representa un conjunto de puntos de datos con sus respectivas coordenadas X e Y. Al agregar varias series, puede comparar y analizar diferentes conjuntos de datos dentro del mismo gráfico de dispersión, proporcionando una vista completa de sus datos.

#### Q3. ¿Puedo personalizar la apariencia del gráfico de dispersión?
Sí, con Aspose.Words para .NET, puede personalizar varios aspectos de la apariencia del gráfico de dispersión. Puede modificar propiedades como el color de la serie, la forma del marcador, las etiquetas de los ejes y el formato del área del gráfico. La biblioteca proporciona un amplio conjunto de API para controlar los elementos visuales del gráfico y crear una apariencia personalizada que se adapte a sus necesidades.

#### Q4. ¿Puedo guardar el documento con el gráfico de dispersión insertado en diferentes formatos?
Sí, Aspose.Words para .NET le permite guardar el documento con el gráfico de dispersión insertado en varios formatos, como DOCX, PDF, HTML y más. Puede elegir el formato de salida deseado en función de sus requisitos y utilizar el`Save` metodo de la`Document` objeto para guardar el documento. El gráfico de dispersión insertado se conservará en el documento guardado.

#### P5. ¿Puedo modificar los datos y la apariencia del gráfico de dispersión después de insertarlo?
Sí, después de insertar el gráfico de dispersión en el documento, puede modificar sus datos y apariencia utilizando las API proporcionadas por Aspose.Words para .NET. Puede actualizar los datos de la serie con nuevas coordenadas X e Y, cambiar las formas y los colores de los marcadores, personalizar las propiedades de los ejes y aplicar opciones de formato para crear gráficos dinámicos e interactivos en sus documentos de Word.