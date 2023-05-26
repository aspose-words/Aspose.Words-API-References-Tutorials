---
title: Insertar gráfico de burbujas
linktitle: Insertar gráfico de burbujas
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un gráfico de burbujas en un documento con Aspose.Words para .NET. Agregue datos de serie con valores de tamaño de burbuja, X e Y.
type: docs
weight: 10
url: /es/net/programming-with-charts/insert-bubble-chart/
---

Este tutorial explica cómo usar Aspose.Words para .NET para insertar un gráfico de burbujas en un documento. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y guardar el documento.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo del sitio web oficial de Aspose o usar el administrador de paquetes NuGet para instalarlo.
- Una ruta de directorio del documento donde se guardará el documento de salida.

## Paso 2: Cree un nuevo documento e inserte un gráfico

 Crear un nuevo`Document` objeto y un`DocumentBuilder` para construir el documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 A continuación, utilice el`InsertChart` metodo de la`DocumentBuilder` para insertar un gráfico de burbujas en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: Agregar datos de series al gráfico

Agregue datos de serie al gráfico. En este ejemplo, agregaremos tres puntos de datos con los valores correspondientes de X, Y y tamaño de burbuja.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## Paso 4: Guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

Esto completa la implementación de insertar un gráfico de burbujas usando Aspose.Words para .NET.

### Ejemplo de código fuente para Insertar gráfico de burbujas usando Aspose.Words para .NET 

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```