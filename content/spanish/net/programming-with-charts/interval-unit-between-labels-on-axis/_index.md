---
title: Unidad de intervalo entre etiquetas en el eje de un gráfico
linktitle: Unidad de intervalo entre etiquetas en el eje de un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar la unidad de intervalo entre etiquetas en el eje de un gráfico usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Este tutorial explica cómo usar Aspose.Words para .NET para establecer la unidad de intervalo entre etiquetas en el eje de un gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y personalizar las etiquetas de los ejes.

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

 A continuación, utilice el`InsertChart` método de la`DocumentBuilder` para insertar un gráfico de columnas en el documento.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Paso 3: agregar datos de la serie al gráfico

Agregue datos de series al gráfico. En este ejemplo, agregaremos cinco elementos con sus valores correspondientes.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Paso 4: personaliza las etiquetas de los ejes

 Para configurar la unidad de intervalo entre etiquetas en el eje X, acceda a la`AxisX` propiedad del gráfico y establecer el`TickLabelSpacing` propiedad al valor deseado. En este ejemplo, configuramos el espaciado en 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Paso 5: guarde el documento

 Finalmente, guarde el documento en el directorio especificado usando el`Save` método de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Esto completa la implementación de configurar la unidad de intervalo entre etiquetas en el eje usando Aspose.Words para .NET.

### Código fuente de ejemplo para unidad de intervalo entre etiquetas en eje usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

## Conclusión

En este tutorial, aprendió cómo configurar la unidad de intervalo entre etiquetas en el eje de un gráfico usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, puede crear un nuevo documento, insertar un gráfico de columnas, agregar datos de series y personalizar las etiquetas de los ejes para controlar el espacio entre las etiquetas.

Aspose.Words para .NET proporciona potentes funciones para manipular gráficos en documentos de Word. Al configurar la unidad de intervalo entre etiquetas en el eje, puede controlar la densidad de visualización de las etiquetas y mejorar la legibilidad de sus gráficos. Esto le permite optimizar la presentación de datos y mejorar la experiencia general del usuario.

Con Aspose.Words para .NET, tiene la flexibilidad de personalizar varios aspectos del gráfico, incluidas las etiquetas de los ejes. Puede configurar la unidad de intervalo deseada para garantizar que las etiquetas estén espaciadas adecuadamente y proporcionen una representación clara de los puntos de datos.

### Preguntas frecuentes

#### P1. ¿Qué son las etiquetas de los ejes en un gráfico?
Las etiquetas de los ejes en un gráfico se refieren a la representación textual de los valores a lo largo del eje horizontal (eje X) o vertical (eje Y) del gráfico. Estas etiquetas ayudan a identificar e interpretar los puntos de datos trazados en el gráfico. Las etiquetas de los ejes proporcionan contexto y permiten a los usuarios comprender la escala y el rango de valores del gráfico.

#### P2. ¿Cómo puedo personalizar el espacio entre las etiquetas de los ejes?
 Para personalizar el espacio entre las etiquetas de los ejes en un gráfico usando Aspose.Words para .NET, puede acceder a`AxisX` o`AxisY` propiedad del gráfico y modificar la`TickLabelSpacing` propiedad. Al configurar el`TickLabelSpacing` a un valor específico, puede controlar la unidad de intervalo entre las etiquetas en el eje respectivo, ajustando el espaciado según sus requisitos.

#### P3. ¿Puedo establecer un espaciado diferente para las etiquetas del eje X y del eje Y?
Sí, puede establecer un espaciado diferente para las etiquetas del eje X y del eje Y usando Aspose.Words para .NET. Acceda al eje respectivo (`AxisX` para el eje X o`AxisY` para el eje Y) del gráfico y modificar el`TickLabelSpacing`propiedad individualmente para cada eje. Esto le permite tener diferentes unidades de intervalo y espaciado para las etiquetas en los ejes X e Y, lo que proporciona un control detallado sobre la apariencia del gráfico.

#### P4. ¿Cuál es el significado de la unidad de intervalo entre etiquetas en el eje?
La unidad de intervalo entre etiquetas en el eje determina el espacio entre etiquetas consecutivas que se muestran en el gráfico. Al configurar la unidad de intervalo, puede controlar la densidad de las etiquetas y asegurarse de que estén espaciadas adecuadamente para evitar el hacinamiento y la superposición. Ajustar la unidad de intervalo le permite presentar los datos de una manera más legible y visualmente atractiva.

#### P5. ¿Puedo modificar otras propiedades de las etiquetas de los ejes?
Sí, Aspose.Words para .NET proporciona una amplia gama de propiedades para personalizar la apariencia y el comportamiento de las etiquetas de los ejes. Puede modificar propiedades como fuente, tamaño, color, orientación, alineación y más para lograr el formato y estilo deseados para las etiquetas de los ejes. La biblioteca ofrece un amplio control sobre los elementos del gráfico, lo que le permite crear gráficos de aspecto profesional adaptados a sus requisitos específicos.