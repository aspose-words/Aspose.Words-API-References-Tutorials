---
title: Límites del eje en un gráfico
linktitle: Límites del eje en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a establecer los límites de un eje en un gráfico usando Aspose.Words para .NET controlando el rango de valores mostrados en el eje.
type: docs
weight: 10
url: /es/net/programming-with-charts/bounds-of-axis/
---
## Introducción

¿Está buscando crear documentos profesionales con gráficos en .NET? ¡Estás en el lugar correcto! Esta guía lo guiará a través del proceso de uso de Aspose.Words para .NET para establecer los límites del eje en un gráfico. Desglosaremos cada paso para asegurarnos de que pueda seguirlo fácilmente, incluso si es nuevo en la biblioteca. Entonces, ¡sumergámonos y comencemos!

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

-  Aspose.Words para .NET: puedes[descargar](https://releases.aspose.com/words/net/) la última versión o utilizar una[prueba gratuita](https://releases.aspose.com/).
- .NET Framework: asegúrese de tener .NET instalado en su sistema.
- IDE: un entorno de desarrollo como Visual Studio.

Una vez que tengas todo listo, podemos pasar a los siguientes pasos.

## Importar espacios de nombres

Para comenzar, deberá importar los espacios de nombres necesarios. Estos le permitirán acceder a la biblioteca Aspose.Words y sus funciones de gráficos.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Paso 1: configure su directorio de documentos

Lo primero es lo primero, debe configurar el directorio donde se guardará su documento. Este es un paso simple pero crucial para organizar sus archivos.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cree un nuevo documento

A continuación, cree un nuevo objeto de documento. Este documento servirá como contenedor para su gráfico.

```csharp
Document doc = new Document();
```

## Paso 3: Inicialice el Generador de documentos

La clase DocumentBuilder proporciona una forma rápida y sencilla de crear documentos. Inicialícelo con su documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 4: insertar un gráfico

Ahora es el momento de insertar un gráfico en su documento. En este ejemplo, usaremos un gráfico de columnas.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 5: borrar series existentes

Para asegurarse de comenzar desde cero, borre cualquier serie existente del gráfico.

```csharp
chart.Series.Clear();
```

## Paso 6: agregar datos al gráfico

Aquí, agregamos datos al gráfico. Esto incluye especificar el nombre de la serie y los puntos de datos.

```csharp
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Paso 7: establecer los límites del eje

Establecer los límites del eje Y garantiza que el gráfico tenga la escala correcta.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Paso 8: guarde el documento

Finalmente, guarde su documento en el directorio especificado.

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

¡Y eso es todo! Ha creado con éxito un documento con un gráfico utilizando Aspose.Words para .NET. 

## Conclusión

Con Aspose.Words para .NET, puede crear y manipular gráficos en sus documentos fácilmente. Esta guía paso a paso le ha mostrado cómo establecer los límites del eje en un gráfico, haciendo que su presentación de datos sea más precisa y profesional. Ya sea que esté generando informes, presentaciones o cualquier otro documento, Aspose.Words proporciona las herramientas que necesita.

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una biblioteca que le permite crear, modificar y convertir documentos de Word mediante programación utilizando el marco .NET.

### ¿Cómo configuro Aspose.Words para .NET?
 Puedes descargarlo desde[aquí](https://releases.aspose.com/words/net/) y siga las instrucciones de instalación proporcionadas.

### ¿Puedo utilizar Aspose.Words gratis?
 Sí, puedes usar un[prueba gratuita](https://releases.aspose.com/) o conseguir un[licencia temporal](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo encontrar documentación para Aspose.Words para .NET?
 La documentación detallada está disponible.[aquí](https://reference.aspose.com/words/net/).

### ¿Cómo puedo obtener soporte para Aspose.Words?
 Puedes visitar el[foro de soporte](https://forum.aspose.com/c/words/8) para obtener ayuda.