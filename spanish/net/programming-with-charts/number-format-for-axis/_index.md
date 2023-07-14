---
title: Formato de número para eje en un gráfico
linktitle: Formato de número para eje en un gráfico
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a configurar el formato de número para un eje en un gráfico usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-charts/number-format-for-axis/
---

Este tutorial explica cómo usar Aspose.Words para .NET para establecer el formato de número para un eje en un gráfico. El código fuente proporcionado demuestra cómo crear un gráfico, agregar datos de series y dar formato a las etiquetas de los ejes.

## Paso 1: configurar el proyecto

Asegúrese de tener los siguientes requisitos previos:

- Aspose.Words para la biblioteca .NET instalada. Puede descargarlo utilizando el administrador de paquetes NuGet para instalarlo.
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
	//Ruta a su directorio de documentos
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

## Conclusión

En este tutorial, aprendió cómo configurar el formato de número para un eje en un gráfico usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, puede crear un nuevo documento, insertar un gráfico de columnas, agregar datos de serie y formatear las etiquetas de los ejes para mostrar números en un formato específico.

Aspose.Words para .NET proporciona potentes funciones para personalizar la apariencia de los gráficos en documentos de Word. Al configurar el formato de número para las etiquetas de los ejes, puede controlar cómo se muestran los números, incluidas opciones como lugares decimales, separadores de miles, símbolos de moneda y más. Esto le permite presentar datos numéricos de una manera clara y significativa.

Con Aspose.Words para .NET, tiene la flexibilidad de formatear varios aspectos del gráfico, incluidas las etiquetas de los ejes. Al establecer el formato de número para el eje, puede garantizar la coherencia y mejorar la legibilidad del gráfico, lo que facilita a los usuarios la interpretación de los valores representados.

### preguntas frecuentes

#### Q1. ¿Cuál es el formato de número para un eje en un gráfico?
El formato de número para un eje en un gráfico se refiere al formato aplicado a los valores numéricos que se muestran en el eje. Le permite controlar cómo se presentan los números, incluidas opciones como lugares decimales, separadores de miles, símbolos de moneda, signos de porcentaje y más. Al establecer el formato de número, puede personalizar la apariencia de los datos numéricos en el gráfico para que se adapte a sus requisitos específicos.

#### Q2. ¿Cómo puedo establecer el formato de número para las etiquetas de los ejes?
 Para establecer el formato de número para las etiquetas de los ejes en un gráfico usando Aspose.Words para .NET, puede acceder a la`AxisY` propiedad del gráfico y establecer la`NumberFormat.FormatCode`propiedad al código de formato deseado. El código de formato sigue la sintaxis de los patrones de formato numérico estándar y determina cómo se muestran los números. Por ejemplo, puede usar "#,##0.00" para mostrar números con dos decimales y separadores de miles.

#### Q3. ¿Puedo configurar diferentes formatos de números para las etiquetas del eje X y del eje Y?
Sí, puede establecer diferentes formatos de números para las etiquetas del eje X y del eje Y mediante Aspose.Words para .NET. Acceda al eje respectivo (`AxisX` para el eje X o`AxisY` para el eje Y) del gráfico y modifique el`NumberFormat.FormatCode` propiedad individualmente para cada eje. Esto le permite aplicar diferentes formatos de números a las etiquetas de cada eje según sus requisitos específicos.

#### Q4. ¿Cuáles son algunos códigos de formato de número comunes que puedo usar?
Aspose.Words para .NET admite una amplia gama de códigos de formato de número que puede usar para dar formato a las etiquetas de los ejes en un gráfico. Algunos códigos de formato comunes incluyen:

- `0` o`#` - Muestra el número sin decimales.
- `0.00` o`#.00` - Muestra el número con dos decimales.
- `#,##0` Muestra el número con separadores de miles.
- `"€"0.00` - Muestra el número con el símbolo de la moneda Euro y dos decimales.
- `"%"0` - Muestra el número como un porcentaje.

 Puede encontrar más información sobre el número[códigos de formato](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) en Referencia API de Aspose.Words para .NET.

#### P5. ¿Puedo personalizar otras propiedades de las etiquetas de los ejes?
Sí, Aspose.Words para .NET proporciona una amplia gama de propiedades para personalizar la apariencia y el comportamiento de las etiquetas de los ejes. Además del formato de número, puede modificar propiedades como fuente, tamaño, color, orientación, alineación y más. Esto le permite personalizar completamente las etiquetas de los ejes para que coincidan con el estilo y los requisitos de presentación deseados.