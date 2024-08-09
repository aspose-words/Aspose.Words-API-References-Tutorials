---
title: Insertar gráfico de dispersión en un documento de Word
linktitle: Insertar gráfico de dispersión en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar un gráfico de dispersión en Word con Aspose.Words para .NET. Pasos sencillos para integrar representaciones de datos visuales en sus documentos.
type: docs
weight: 10
url: /es/net/programming-with-charts/insert-scatter-chart/
---
## Introducción

En este tutorial, aprenderá cómo aprovechar Aspose.Words para .NET para insertar un gráfico de dispersión en su documento de Word. Los gráficos de dispersión son poderosas herramientas visuales que pueden mostrar de manera efectiva puntos de datos basados en dos variables, lo que hace que sus documentos sean más atractivos e informativos.

## Requisitos previos

Antes de sumergirnos en la creación de gráficos de dispersión con Aspose.Words para .NET, asegúrese de tener los siguientes requisitos previos:

1.  Instalación de Aspose.Words para .NET: Descargue e instale Aspose.Words para .NET desde[aquí](https://releases.aspose.com/words/net/).
   
2. Conocimientos básicos de C#: será beneficiosa la familiaridad con el lenguaje de programación C# y el marco .NET.

## Importar espacios de nombres

Para comenzar, necesita importar los espacios de nombres necesarios en su proyecto C#:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
```

Ahora, analicemos el proceso de insertar un gráfico de dispersión en su documento de Word usando Aspose.Words para .NET:

## Paso 1: Inicialice el documento y DocumentBuilder

 Primero, inicialice una nueva instancia del`Document` clase y`DocumentBuilder` clase para comenzar a construir su documento.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: inserta el gráfico de dispersión

 Utilice el`InsertChart` método de la`DocumentBuilder` clase para insertar un gráfico de dispersión en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: agregar series de datos al gráfico

Ahora, agregue series de datos a su gráfico de dispersión. Este ejemplo demuestra cómo agregar una serie con puntos de datos específicos.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## Paso 4: guarde el documento

 Finalmente, guarde el documento modificado en la ubicación deseada usando el`Save` método de la`Document` clase.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo insertar un gráfico de dispersión en su documento de Word usando Aspose.Words para .NET. Los gráficos de dispersión son herramientas excelentes para visualizar relaciones de datos y, con Aspose.Words, puede integrarlos sin esfuerzo en sus documentos para mejorar la claridad y la comprensión.

## Preguntas frecuentes

### ¿Puedo personalizar la apariencia del gráfico de dispersión usando Aspose.Words?
Sí, Aspose.Words permite una amplia personalización de las propiedades del gráfico, como colores, ejes y etiquetas.

### ¿Aspose.Words es compatible con diferentes versiones de Microsoft Word?
Aspose.Words admite varias versiones de Microsoft Word, lo que garantiza la compatibilidad entre plataformas.

### ¿Aspose.Words proporciona soporte para otros tipos de gráficos?
Sí, Aspose.Words admite una amplia gama de tipos de gráficos, incluidos gráficos de barras, gráficos de líneas y gráficos circulares.

### ¿Puedo actualizar dinámicamente los datos en el gráfico de dispersión mediante programación?
Por supuesto, puede actualizar los datos del gráfico de forma dinámica mediante llamadas a la API de Aspose.Words.

### ¿Dónde puedo obtener más ayuda o soporte para Aspose.Words?
 Para obtener más ayuda, visite el[Foro de soporte de Aspose.Words](https://forum.aspose.com/c/words/8).