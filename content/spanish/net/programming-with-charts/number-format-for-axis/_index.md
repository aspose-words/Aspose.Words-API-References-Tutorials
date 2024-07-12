---
title: Formato numérico para eje en un gráfico
linktitle: Formato numérico para eje en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a formatear los números de los ejes del gráfico usando Aspose.Words para .NET con esta guía paso a paso. Mejore la legibilidad y el profesionalismo de su documento sin esfuerzo.
type: docs
weight: 10
url: /es/net/programming-with-charts/number-format-for-axis/
---
## Introducción

¡Hola! ¿Alguna vez ha trabajado con gráficos en sus documentos y ha deseado poder formatear los números en su eje para que se vean más profesionales? ¡Pues estás de suerte! En este tutorial, profundizaremos en cómo puede lograr precisamente eso usando Aspose.Words para .NET. Esta poderosa biblioteca le permite manejar documentos de Word de una manera muy sencilla. Y hoy, nos centramos en darle un cambio de imagen a esos ejes del gráfico con formatos de números personalizados.

## Requisitos previos

Antes de comenzar, asegurémonos de que tiene todo lo que necesita. Aquí hay una lista de verificación rápida:

-  Aspose.Words para .NET: asegúrese de tenerlo instalado. Si no, puedes[descarguelo aqui](https://releases.aspose.com/words/net/).
- .NET Framework: asegúrese de tener instalado un .NET framework compatible.
- Entorno de desarrollo: un IDE como Visual Studio funcionará perfectamente.
- Conocimientos básicos de C#: esto le ayudará a seguir los ejemplos de codificación.

## Importar espacios de nombres

Lo primero es lo primero: debe importar los espacios de nombres necesarios en su proyecto. Esto es como poner los cimientos antes de construir una casa. Agregue las siguientes directivas de uso en la parte superior de su archivo de código:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Reporting;
```

Ahora, dividamos el proceso en pasos simples y fáciles de seguir.

## Paso 1: configurar el documento

Título: Inicialice su documento

Primero, necesita crear un nuevo documento y un generador de documentos. Piense en este paso como preparar el lienzo y el pincel antes de comenzar su obra maestra.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aquí,`dataDir` es la ruta al directorio de documentos donde guardará el archivo final.`Document`y`DocumentBuilder` son clases de Aspose.Words que le ayudan a crear y manipular documentos de Word.

## Paso 2: insertar un gráfico

Título: Agregue un gráfico a su documento

continuación, agreguemos un gráfico a su documento. Aquí es donde comienza la magia. Insertaremos un gráfico de columnas que actuará como nuestro lienzo en blanco.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

 El`InsertChart` El método inserta un gráfico del tipo especificado (columna en este caso) y dimensiones en el documento.

## Paso 3: Personalizar la serie de gráficos

Título: Llene su gráfico con datos

Ahora, necesitamos agregar algunos datos a nuestro gráfico. Este paso es similar a llenar su gráfico con información significativa.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

 Aquí, agregamos una nueva serie llamada "Aspose Series 1" con cinco puntos de datos. El`Series.Clear` El método garantiza que se eliminen todos los datos preexistentes antes de agregar nuestra nueva serie.

## Paso 4: formatear los números de eje

Título: Embellezca los números de sus ejes

Finalmente, formateemos los números en el eje Y para hacerlos más legibles. Esto es como darle los toques finales a tu obra de arte.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

 El`FormatCode` La propiedad le permite establecer un formato personalizado para los números en el eje. En este ejemplo,`#,##0`garantiza que los números grandes se muestren con comas para los miles.

## Paso 5: guardar el documento

Título: Guarde su obra maestra

Ahora que todo está configurado, es hora de guardar su documento. Este paso es la gran revelación de su trabajo.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

 Aquí el`Save` El método guarda el documento en la ruta especificada con el nombre de archivo.`WorkingWithCharts.NumberFormatForAxis.docx`.

## Conclusión

¡Y ahí lo tienes! Ha formateado correctamente los números en el eje Y de su gráfico utilizando Aspose.Words para .NET. Esto no sólo hace que sus gráficos luzcan más profesionales sino que también mejora la legibilidad. Aspose.Words ofrece una gran cantidad de funciones que pueden ayudarle a crear impresionantes documentos de Word mediante programación. Entonces, ¿por qué no explorar más y ver qué más puedes hacer?

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una poderosa biblioteca que permite a los desarrolladores crear, manipular y convertir documentos de Word mediante programación.

### ¿Puedo formatear otros aspectos del gráfico además de los números de eje?
¡Absolutamente! Aspose.Words para .NET le permite formatear títulos, etiquetas e incluso personalizar la apariencia del gráfico.

### ¿Hay una prueba gratuita disponible para Aspose.Words para .NET?
 Sí, puedes conseguir un[prueba gratuita aquí](https://releases.aspose.com/).

### ¿Puedo usar Aspose.Words para .NET con otros lenguajes .NET además de C#?
Sí, Aspose.Words para .NET es compatible con cualquier lenguaje .NET, incluidos VB.NET y F#.

### ¿Dónde puedo encontrar documentación más detallada?
 La documentación detallada está disponible en el[Página de documentación de Aspose.Words para .NET](https://reference.aspose.com/words/net/).
