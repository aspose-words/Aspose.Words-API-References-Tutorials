---
title: Dar formato al número de etiqueta de datos en un gráfico
linktitle: Dar formato al número de etiqueta de datos en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a formatear etiquetas de datos en gráficos usando Aspose.Words para .NET con esta guía paso a paso. Mejore sus documentos de Word sin esfuerzo.
type: docs
weight: 10
url: /es/net/programming-with-charts/format-number-of-data-label/
---
## Introducción

La creación de documentos atractivos e informativos a menudo implica incluir gráficos con etiquetas de datos bien formateadas. Si es un desarrollador de .NET y busca mejorar sus documentos de Word con gráficos sofisticados, Aspose.Words para .NET es una biblioteca fantástica que lo ayudará a lograrlo. Este tutorial lo guiará a través del proceso de formatear etiquetas numéricas en un gráfico usando Aspose.Words para .NET, paso a paso.

## Requisitos previos

Antes de profundizar en el código, existen algunos requisitos previos que debe cumplir:

-  Aspose.Words para .NET: asegúrese de tener instalada la biblioteca Aspose.Words para .NET. Si aún no lo has instalado, puedes[descárgalo aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: debe tener configurado un entorno de desarrollo .NET. Se recomienda encarecidamente Visual Studio.
- Conocimientos básicos de C#: la familiaridad con la programación en C# es esencial ya que este tutorial implica escribir y comprender el código C#.
-  Licencia temporal: para utilizar Aspose.Words sin limitaciones, puede obtener una[licencia temporal](https://purchase.aspose.com/temporary-license/).

Ahora, profundicemos en el proceso paso a paso de formatear etiquetas numéricas en un gráfico.

## Importar espacios de nombres

Lo primero es lo primero, necesitamos importar los espacios de nombres necesarios para trabajar con Aspose.Words para .NET. Agregue las siguientes líneas en la parte superior de su archivo C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Paso 1: configure su directorio de documentos

Antes de que pueda comenzar a manipular su documento de Word, debe especificar el directorio donde se guardará su documento. Esto es esencial para la operación de guardar más adelante.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

## Paso 2: Inicialice el documento y DocumentBuilder

 El siguiente paso es inicializar un nuevo`Document` y un`DocumentBuilder` . El`DocumentBuilder` es una clase auxiliar que nos permite construir el contenido del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: inserte un gráfico en el documento

 Ahora, insertemos un gráfico en el documento usando el`DocumentBuilder`. En este tutorial, usaremos un gráfico de líneas como ejemplo.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

Aquí, insertamos un gráfico de líneas con un ancho y alto específicos y configuramos el título del gráfico.

## Paso 4: borre la serie predeterminada y agregue una nueva serie

De forma predeterminada, el gráfico tendrá algunas series pregeneradas. Necesitamos borrarlos y agregar nuestra propia serie con puntos de datos específicos.

```csharp
// Eliminar series generadas por defecto.
chart.Series.Clear();

// Agregue nuevas series con puntos de datos personalizados.
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
	new string[] { "Category 1", "Category 2", "Category 3" }, 
	new double[] { 2.5, 1.5, 3.5 });
```

## Paso 5: habilite las etiquetas de datos

Para mostrar las etiquetas de datos en el gráfico, debemos habilitarlas para nuestra serie.

```csharp
series1.HasDataLabels = true;
series1.DataLabels.ShowValue = true;
```

## Paso 6: Formatear etiquetas de datos

El núcleo de este tutorial es formatear las etiquetas de datos. Podemos aplicar diferentes formatos de números a cada etiqueta de datos individualmente.

```csharp
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00"; // Formato de moneda
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy"; // Formato de fecha
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%"; // Formato de porcentaje
```

 Además, puede vincular el formato de una etiqueta de datos a una celda de origen. Cuando se vincula, el`NumberFormat` se restablecerá a general y se heredará de la celda de origen.

```csharp
series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
```

## Paso 7: guarde el documento

Finalmente, guarde el documento en el directorio especificado.

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

Esto guarda su documento con el nombre especificado y garantiza que se conserve su gráfico con etiquetas de datos formateadas.

## Conclusión

Formatear etiquetas de datos en un gráfico usando Aspose.Words para .NET puede mejorar en gran medida la legibilidad y el profesionalismo de sus documentos de Word. Si sigue esta guía paso a paso, ahora debería poder crear un gráfico, agregar series de datos y formatear las etiquetas de datos para satisfacer sus necesidades. Aspose.Words para .NET es una poderosa herramienta que permite una amplia personalización y automatización de documentos de Word, lo que la convierte en un activo invaluable para los desarrolladores de .NET.

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una poderosa biblioteca para crear, manipular y convertir documentos de Word mediante programación usando C#.

### ¿Puedo formatear otros tipos de gráficos con Aspose.Words para .NET?
Sí, Aspose.Words para .NET admite una variedad de tipos de gráficos, incluidos barras, columnas, circulares y más.

### ¿Cómo obtengo una licencia temporal de Aspose.Words para .NET?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).

### ¿Es posible vincular etiquetas de datos a celdas de origen en Excel?
Sí, puede vincular etiquetas de datos a celdas de origen, lo que permite que el formato numérico se herede de la celda de origen.

### ¿Dónde puedo encontrar documentación más detallada sobre Aspose.Words para .NET?
 Puedes encontrar documentación completa.[aquí](https://reference.aspose.com/words/net/).
