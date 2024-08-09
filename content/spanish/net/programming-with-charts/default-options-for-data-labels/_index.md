---
title: Establecer opciones predeterminadas para etiquetas de datos en un gráfico
linktitle: Establecer opciones predeterminadas para etiquetas de datos en un gráfico
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar opciones predeterminadas para etiquetas de datos en un gráfico usando Aspose.Words para .NET. Siga nuestra guía paso a paso para crear y personalizar gráficos sin esfuerzo.
type: docs
weight: 10
url: /es/net/programming-with-charts/default-options-for-data-labels/
---
## Introducción

¡Hola! ¿Estás emocionado de sumergirte en el mundo de la automatización de documentos? Hoy, exploraremos cómo usar Aspose.Words para .NET para crear documentos impresionantes mediante programación. Aspose.Words es una biblioteca poderosa que le permite manipular documentos de Word con facilidad y, en este tutorial, nos centraremos en configurar opciones predeterminadas para etiquetas de datos en un gráfico. Ya sea que sea un desarrollador experimentado o un novato, esta guía lo guiará a través de cada paso para que pueda comenzar a trabajar en poco tiempo.

## Requisitos previos

Antes de comenzar, asegurémonos de que tiene todo lo que necesita para seguir este tutorial. Aquí hay una lista de verificación rápida:

- Visual Studio o cualquier otro IDE compatible con .NET: aquí es donde escribirás y ejecutarás tu código.
-  Aspose.Words para .NET: puedes[descargar la última versión](https://releases.aspose.com/words/net/) e instalarlo en su proyecto.
- Conocimientos básicos de programación en C#: si bien esta guía es apta para principiantes, será útil un poco de familiaridad con C#.
- .NET Framework instalado: asegúrese de tener .NET Framework configurado en su máquina.
-  Una licencia temporal para Aspose.Words: obtenga una[aquí](https://purchase.aspose.com/temporary-license/) para desbloquear la funcionalidad completa.

Una vez que haya ordenado estos requisitos previos, ¡estamos listos para comenzar!

## Importar espacios de nombres

Primero lo primero, configuremos nuestro proyecto e importemos los espacios de nombres necesarios. Estos espacios de nombres son cruciales para acceder a la funcionalidad Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.ReportingServices;
```

## Paso 1: crear un nuevo documento


 El viaje comienza creando un nuevo documento e inicializando un`DocumentBuilder` . El`DocumentBuilder` La clase proporciona un conjunto de métodos para manipular el contenido del documento fácilmente.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crear un nuevo documento
Document doc = new Document();

// Inicializar DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Explicación

 En este paso, hemos configurado el documento y el generador que usaremos para insertar y formatear nuestro contenido. El`dataDir` La variable contiene la ruta donde guardaremos nuestro documento final.

## Paso 2: insertar un gráfico

 A continuación, agregaremos un gráfico circular a nuestro documento. El`InsertChart` método de la`DocumentBuilder` La clase hace que esto sea súper fácil.

```csharp
// Insertar un gráfico circular
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);

// Acceder al objeto del gráfico
Chart chart = shape.Chart;
```

### Explicación

Aquí, estamos insertando un gráfico circular en nuestro documento. El`InsertChart` El método requiere el tipo de gráfico, el ancho y el alto como parámetros. Después de insertar el gráfico, accedemos al objeto del gráfico para manipularlo aún más.

## Paso 3: personaliza la serie de gráficos

Ahora, borraremos cualquier serie existente en el gráfico y agregaremos nuestra serie personalizada. Esta serie representará nuestros puntos de datos.

```csharp
// Borrar series de gráficos existentes
chart.Series.Clear();

// Agregar nueva serie al gráfico
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

### Explicación

En este paso, nos aseguramos de que nuestro gráfico esté vacío borrando cualquier serie preexistente. Luego, agregamos una nueva serie con categorías y valores personalizados, que se mostrarán en nuestro gráfico circular.

## Paso 4: Establecer opciones predeterminadas para etiquetas de datos

Las etiquetas de datos son cruciales para que su gráfico sea informativo. Configuraremos opciones para mostrar porcentaje, valor y personalizaremos el separador.

```csharp
// Acceder a la colección de etiquetas de datos
ChartDataLabelCollection labels = series.DataLabels;

// Establecer opciones de etiqueta de datos
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

### Explicación

 Aquí estamos accediendo al`DataLabels`propiedad de nuestra serie para personalizar la apariencia y la información que se muestra en cada etiqueta de datos. Hemos elegido mostrar tanto el porcentaje como el valor, ocultar las líneas guía y establecer un separador personalizado.

## Paso 5: guarde el documento

Finalmente, guardaremos nuestro documento en el directorio especificado. Este paso garantiza que todos nuestros cambios se escriban en un archivo.

```csharp
// guardar el documento
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

### Explicación

 En este último paso guardamos nuestro documento usando el`Save` método. El documento se guardará en el directorio especificado por`dataDir`, con el nombre "WorkingWithCharts.DefaultOptionsForDataLabels.docx".

## Conclusión

¡Y ahí lo tienes! Ha creado con éxito un documento de Word con un gráfico circular personalizado utilizando Aspose.Words para .NET. Esta poderosa biblioteca facilita la automatización de la creación y manipulación de documentos, ahorrándole tiempo y esfuerzo. Ya sea que esté generando informes, facturas o cualquier otro tipo de documento, Aspose.Words lo tiene cubierto.

 Siéntete libre de explorar el[Documentación de Aspose.Words](https://reference.aspose.com/words/net/) para más características y ejemplos. ¡Feliz codificación!

## Preguntas frecuentes

### ¿Puedo utilizar Aspose.Words gratis?
Puedes usar Aspose.Words gratis con un[licencia temporal](https://purchase.aspose.com/temporary-license/) o explorar sus características utilizando el[prueba gratuita](https://releases.aspose.com/).

### ¿Cómo obtengo soporte para Aspose.Words?
 Puedes obtener soporte a través del[Foro de soporte de Aspose.Words](https://forum.aspose.com/c/words/8).

### ¿Puedo agregar otros tipos de gráficos?
 Sí, Aspose.Words admite varios tipos de gráficos, como gráficos de barras, líneas y columnas. Compruebe el[documentación](https://reference.aspose.com/words/net/) para más detalles.

### ¿Aspose.Words es compatible con .NET Core?
 Sí, Aspose.Words es compatible con .NET Core. Puedes encontrar más información en el[documentación](https://reference.aspose.com/words/net/).

### ¿Cómo puedo comprar una licencia para Aspose.Words?
 Puede adquirir una licencia en el[tienda aspose](https://purchase.aspose.com/buy).

