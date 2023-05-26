---
title: Formato de número para eje
linktitle: Formato de número para eje
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a configurar el formato de número para un eje en un gráfico usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/number-format-for-axis/
---

Este tutorial explica cómo usar Aspose.Words para .NET para establecer el formato de número para un eje en un gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y dar formato a las etiquetas de los ejes.

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

 A continuación, utilice el`InsertChart` metodo de la`DocumentBuilder` para insertar un gráfico de columnas en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: Agregar datos de series al gráfico

Agregue datos de serie al gráfico. En este ejemplo, agregaremos cinco elementos con sus valores correspondientes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Paso 4: Dar formato a las etiquetas de los ejes

 Para establecer el formato de número para las etiquetas del eje Y, acceda al`AxisY` propiedad del gráfico y establecer la`NumberFormat.FormatCode` propiedad al formato deseado. En este ejemplo, configuramos el formato en "#,##0" para mostrar números con separadores de miles.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Paso 5: Guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Esto completa la implementación de la configuración del formato de número para el eje mediante Aspose.Words para .NET.

### Ejemplo de código fuente para Number Format For Axis usando Aspose.Words para .NET 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```