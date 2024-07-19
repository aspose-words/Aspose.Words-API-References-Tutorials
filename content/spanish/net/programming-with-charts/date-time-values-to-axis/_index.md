---
title: Agregar valores de fecha y hora al eje de un gráfico
linktitle: Agregar valores de fecha y hora al eje de un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo agregar valores de fecha y hora al eje de un gráfico usando Aspose.Words para .NET en esta guía completa paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-charts/date-time-values-to-axis/
---
## Introducción

Crear gráficos en documentos puede ser una forma poderosa de visualizar datos. Cuando se trata de datos de series temporales, agregar valores de fecha y hora al eje de un gráfico es crucial para mayor claridad. En este tutorial, lo guiaremos a través del proceso de agregar valores de fecha y hora al eje de un gráfico usando Aspose.Words para .NET. Esta guía paso a paso lo ayudará a configurar su entorno, escribir el código y comprender cada parte del proceso. ¡Vamos a sumergirnos!

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

1. Visual Studio o cualquier IDE .NET: necesita un entorno de desarrollo para escribir y ejecutar su código .NET.
2.  Aspose.Words para .NET: Debe tener instalada la biblioteca Aspose.Words para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/words/net/).
3. Conocimientos básicos de C#: este tutorial asume que tienes conocimientos básicos de programación en C#.
4.  Una licencia Aspose válida: puede obtener una licencia temporal de[aquí](https://purchase.aspose.com/temporary-license/).

## Importar espacios de nombres

Para comenzar, asegúrese de haber importado los espacios de nombres necesarios en su proyecto. Este paso es crucial para acceder a las clases y métodos de Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Paso 1: configure su directorio de documentos

Primero, debe definir el directorio donde se guardará su documento. Esto es importante para organizar sus archivos y garantizar que su código se ejecute correctamente.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cree un nuevo documento y DocumentBuilder

 A continuación, cree una nueva instancia de`Document` clase y un`DocumentBuilder` objeto. Estos objetos le ayudarán a crear y manipular su documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: inserte un gráfico en el documento

 Ahora, inserte un gráfico en su documento usando el`DocumentBuilder` objeto. En este ejemplo, utilizamos un gráfico de columnas, pero también puedes elegir otros tipos.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 4: borrar series existentes

Borre cualquier serie existente en el gráfico para asegurarse de comenzar desde cero. Este paso es esencial para los datos personalizados.

```csharp
chart.Series.Clear();
```

## Paso 5: agregar valores de fecha y hora a la serie

Agregue sus valores de fecha y hora a la serie de gráficos. Este paso implica la creación de matrices para fechas y valores correspondientes.

```csharp
chart.Series.Add("Aspose Series 1",
    new[]
    {
        new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
        new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
    },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Paso 6: configurar el eje X

Establezca la escala y las marcas para el eje X. Esto garantiza que sus fechas se muestren correctamente y en intervalos adecuados.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Paso 7: guarde el documento

Finalmente, guarde su documento en el directorio especificado. Este paso concluye el proceso y su documento ahora debería contener un gráfico con valores de fecha y hora en el eje X.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

## Conclusión

Agregar valores de fecha y hora al eje de un gráfico en un documento es un proceso sencillo con Aspose.Words para .NET. Si sigue los pasos descritos en este tutorial, puede crear gráficos claros e informativos que visualicen de manera efectiva datos de series temporales. Ya sea que esté preparando informes, presentaciones o cualquier documento que requiera una representación detallada de datos, Aspose.Words proporciona las herramientas que necesita para tener éxito.

## Preguntas frecuentes

### ¿Puedo utilizar otros tipos de gráficos con Aspose.Words para .NET?

Sí, Aspose.Words admite varios tipos de gráficos, incluidos líneas, barras, circulares y más.

### ¿Cómo puedo personalizar la apariencia de mi gráfico?

Puede personalizar la apariencia accediendo a las propiedades del gráfico y configurando estilos, colores y más.

### ¿Es posible agregar varias series a un gráfico?

 ¡Absolutamente! Puede agregar varias series a su gráfico llamando al`Series.Add` método varias veces con diferentes datos.

### ¿Qué pasa si necesito actualizar los datos del gráfico dinámicamente?

Puede actualizar los datos del gráfico dinámicamente manipulando las propiedades de la serie y el eje mediante programación según sus requisitos.

### ¿Dónde puedo encontrar documentación más detallada sobre Aspose.Words para .NET?

 Puedes encontrar documentación más detallada.[aquí](https://reference.aspose.com/words/net/).