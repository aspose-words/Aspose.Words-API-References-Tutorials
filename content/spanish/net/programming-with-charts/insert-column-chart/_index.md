---
title: Insertar gráfico de columnas en un documento de Word
linktitle: Insertar gráfico de columnas en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar un gráfico de columnas en un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/insert-column-chart/
---

Este tutorial explica cómo usar Aspose.Words para .NET para insertar un gráfico de columnas en un documento. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y guardar el documento.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo utilizando el administrador de paquetes NuGet para instalarlo.
- Una ruta del directorio de documentos donde se guardará el documento de salida.

## Paso 2: cree un nuevo documento e inserte un gráfico.

 Crear un nuevo`Document` objeto y un`DocumentBuilder` para construir el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A continuación, utilice el`InsertChart` método de la`DocumentBuilder` para insertar un gráfico de columnas en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: agregar datos de la serie al gráfico

Agregue datos de series al gráfico. En este ejemplo, agregaremos dos categorías y sus valores correspondientes.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## Paso 4: guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` método de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

Esto completa la implementación de insertar un gráfico de columnas usando Aspose.Words para .NET.

### Código fuente de ejemplo para Insertar gráfico de columnas usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## Conclusión

En este tutorial, aprendió cómo insertar un gráfico de columnas en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, puede crear un nuevo documento, insertar un gráfico de columnas, agregar datos de series y guardar el documento con el gráfico.

Aspose.Words para .NET proporciona una potente API para el procesamiento de textos con gráficos en documentos de Word. Los gráficos de columnas se utilizan comúnmente para mostrar y comparar datos en diferentes categorías o grupos. Con Aspose.Words para .NET, puede crear fácilmente gráficos de columnas que visualicen sus datos de manera efectiva y brinden información valiosa.

Al utilizar Aspose.Words para .NET, puede automatizar el proceso de generación de documentos con gráficos de columnas, ahorrando tiempo y esfuerzo en la creación manual de documentos. La biblioteca ofrece una amplia gama de tipos de gráficos y opciones de personalización, lo que le permite crear gráficos visualmente atractivos y ricos en datos en sus documentos de Word.

### Preguntas frecuentes

#### P1. ¿Qué es un gráfico de columnas?
Un gráfico de columnas es un tipo de gráfico que representa datos en barras o columnas verticales. Cada columna normalmente representa una categoría o grupo, y la altura o longitud de la columna indica el valor de los datos asociados con esa categoría. Los gráficos de columnas se utilizan comúnmente para comparar datos entre diferentes categorías o para realizar un seguimiento de los cambios a lo largo del tiempo.

#### P2. ¿Puedo agregar varias series al gráfico de columnas?
Sí, puede agregar varias series al gráfico de columnas usando Aspose.Words para .NET. Cada serie representa un conjunto de puntos de datos con sus respectivas categorías y valores. Al agregar varias series, puede comparar y analizar diferentes conjuntos de datos dentro del mismo gráfico, lo que proporciona una vista completa de sus datos.

#### P3. ¿Puedo personalizar la apariencia del gráfico de columnas?
Sí, al utilizar Aspose.Words para .NET, puede personalizar varios aspectos de la apariencia del gráfico de columnas. Puede modificar propiedades como el color de la serie, las etiquetas de los ejes, el ancho de la columna y el formato del área del gráfico. La biblioteca proporciona un amplio conjunto de API para controlar los elementos visuales del gráfico y crear una apariencia personalizada que se adapte a sus necesidades.

#### P4. ¿Puedo guardar el documento con el gráfico de columnas insertado en diferentes formatos?
 Sí, Aspose.Words para .NET le permite guardar el documento con el gráfico de columnas insertado en varios formatos, como DOCX, PDF, HTML y más. Puede elegir el formato de salida deseado según sus requisitos y utilizar el`Save` método de la`Document` objeto para guardar el documento. El gráfico de columnas insertado se conservará en el documento guardado.

#### P5. ¿Puedo modificar los datos y la apariencia del gráfico de columnas después de insertarlo?
Sí, después de insertar el gráfico de columnas en el documento, puede modificar sus datos y su apariencia utilizando las API proporcionadas por Aspose.Words para .NET. Puede actualizar los datos de la serie, cambiar los colores de las columnas, personalizar las propiedades de los ejes y aplicar opciones de formato para crear gráficos dinámicos e interactivos en sus documentos de Word.