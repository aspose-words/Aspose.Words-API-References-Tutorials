---
title: Marque la alineación de etiquetas de varias líneas
linktitle: Marque la alineación de etiquetas de varias líneas
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a alinear etiquetas de varias líneas en un eje de gráfico con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/tick-multi-line-label-alignment/
---

Este tutorial explica cómo usar Aspose.Words para .NET para establecer la alineación de las etiquetas de varias líneas en un eje de gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, acceder al eje y modificar la alineación de la etiqueta de marca.

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

 A continuación, utilice el`InsertChart` metodo de la`DocumentBuilder` para insertar un gráfico de dispersión en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
ChartAxis axis = shape.Chart.AxisX;
```

## Paso 3: establecer la alineación de la etiqueta de marca

 Para configurar la alineación de las etiquetas de varias líneas, acceda a la`AxisX` propiedad del gráfico y establecer la`TickLabelAlignment` propiedad a la alineación deseada. En este ejemplo, establecemos la alineación en`ParagraphAlignment.Right`.

```csharp
axis.TickLabelAlignment = ParagraphAlignment.Right;
```

## Paso 4: Guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` metodo de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```

Esto completa la implementación de la configuración de la alineación de etiquetas de varias líneas de marca mediante Aspose.Words para .NET.

### Ejemplo de código fuente para marcar la alineación de etiquetas de varias líneas usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 450, 250);
	ChartAxis axis = shape.Chart.AxisX;
	// Esta propiedad solo tiene efecto para etiquetas de varias líneas.
	axis.TickLabelAlignment = ParagraphAlignment.Right;
	doc.Save(dataDir + "WorkingWithCharts.TickMultiLineLabelAlignment.docx");
```