---
title: Ocultar eje de gráfico en un documento de Word
linktitle: Ocultar eje de gráfico en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a ocultar el eje del gráfico en un documento usando Aspose.Words para .NET. Oculte el eje para una visualización del gráfico más limpia y enfocada.
type: docs
weight: 10
url: /es/net/programming-with-charts/hide-chart-axis/
---

Este tutorial explica cómo usar Aspose.Words para .NET para ocultar el eje del gráfico en un documento. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y ocultar el eje del gráfico.

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

 A continuación, inserte un gráfico en el documento utilizando el`InsertChart` método de la`DocumentBuilder`. En este ejemplo, insertaremos un gráfico de columnas.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: agregar datos de la serie al gráfico

Agregue datos de series al gráfico. En este ejemplo, agregaremos cinco elementos y sus valores correspondientes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Paso 4: ocultar el eje del gráfico

 Para ocultar el eje del gráfico, acceda a la`AxisY` propiedad del gráfico y establecer el`Hidden`propiedad a`true`.

```csharp
chart.AxisY.Hidden = true;
```

En este ejemplo, ocultamos el eje Y del gráfico.

## Paso 5: guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` método de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Esto completa la implementación de ocultar el eje del gráfico usando Aspose.Words para .NET.

### Código fuente de ejemplo para Ocultar eje del gráfico usando Aspose.Words para .NET 

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
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## Conclusión

En este tutorial, aprendió cómo ocultar el eje del gráfico en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, puede crear un gráfico, agregar datos de series y ocultar el eje del gráfico para lograr el efecto visual deseado.

 Aspose.Words para .NET proporciona una API integral para el procesamiento de palabras con gráficos en documentos de Word, lo que le permite manipular varios aspectos del gráfico, incluidas las propiedades de los ejes. Al acceder al`AxisY` propiedad del gráfico, puede ocultar el eje Y para eliminarlo de la visualización del gráfico.

Ocultar el eje del gráfico puede resultar útil cuando desea centrarse en los datos del gráfico sin la distracción de las líneas y etiquetas del eje. Proporciona una apariencia más limpia y minimalista al gráfico.

Al utilizar Aspose.Words para .NET, puede incorporar fácilmente capacidades de gráficos en sus aplicaciones .NET y generar documentos de apariencia profesional con gráficos personalizados y ejes de gráficos ocultos.

### Preguntas frecuentes

#### P1. ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una potente biblioteca de procesamiento de documentos que permite a los desarrolladores crear, manipular y guardar documentos de Word mediante programación en aplicaciones .NET. Proporciona una amplia gama de funciones para el procesamiento de textos con elementos de documentos, incluidos gráficos y ejes de gráficos.

#### P2. ¿Cómo puedo instalar Aspose.Words para .NET?
Puede instalar Aspose.Words para .NET descargándolo mediante el administrador de paquetes NuGet en Visual Studio. Simplemente busque "Aspose.Words" en el administrador de paquetes NuGet e instálelo en su proyecto.

#### P3. ¿Puedo ocultar tanto el eje X como el eje Y de un gráfico?
 Sí, puede ocultar tanto el eje X como el eje Y de un gráfico usando Aspose.Words para .NET. Para ocultar el eje X, puede acceder a la`AxisX` propiedad del gráfico y establecer el`Hidden`propiedad a`true` . De manera similar, para ocultar el eje Y, puede acceder a la`AxisY` propiedad y establecer el`Hidden`propiedad a`true`. Esto le permite eliminar ambos ejes de la visualización del gráfico.

#### P4. ¿Puedo volver a mostrar el eje después de ocultarlo?
Sí, puede volver a mostrar el eje del gráfico después de ocultarlo usando Aspose.Words para .NET. Para mostrar un eje oculto, simplemente configure el`Hidden` propiedad de la correspondiente`AxisX` o`AxisY` oponerse a`false`. Esto hará que el eje vuelva a ser visible en el gráfico.

#### P5. ¿Puedo personalizar otras propiedades del eje del gráfico?
 Sí, Aspose.Words para .NET le permite personalizar varias propiedades del eje del gráfico, como el título del eje, las etiquetas, el color de la línea y más. Al acceder al`AxisX` y`AxisY` propiedades del gráfico, puede modificar propiedades como`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`, y muchos otros. Esto le brinda un control detallado sobre la apariencia y el comportamiento del eje del gráfico.

#### P6. ¿Puedo guardar el gráfico con el eje oculto en diferentes formatos de archivo?
 Sí, Aspose.Words para .NET le permite guardar el documento que contiene el gráfico con un eje oculto en varios formatos de archivo, como DOCX, PDF, HTML y más. Puede elegir el formato de salida deseado según sus requisitos y utilizar el`Save` método de la`Document` objeto para guardar el documento. El eje oculto se conservará en el documento guardado.