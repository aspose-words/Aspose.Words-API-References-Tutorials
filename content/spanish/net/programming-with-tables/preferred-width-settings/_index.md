---
title: Configuración de ancho preferida
linktitle: Configuración de ancho preferida
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear tablas con configuraciones de ancho absoluto, relativo y automático en Aspose.Words para .NET con esta guía paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-tables/preferred-width-settings/
---
## Introducción

Las tablas son una forma poderosa de organizar y presentar información en sus documentos de Word. Cuando trabaja con tablas en Aspose.Words para .NET, tiene varias opciones para configurar el ancho de las celdas de la tabla para garantizar que se ajusten perfectamente al diseño de su documento. Esta guía lo guiará a través del proceso de creación de tablas con la configuración de ancho preferida usando Aspose.Words para .NET, enfocándose en opciones de tamaño absoluto, relativo y automático. 

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de tener lo siguiente:

1.  Aspose.Words para .NET: asegúrese de tener Aspose.Words para .NET instalado en su entorno de desarrollo. Puedes descargarlo[aquí](https://releases.aspose.com/words/net/).

2. Entorno de desarrollo .NET: tenga configurado un entorno de desarrollo .NET, como Visual Studio.

3. Conocimientos básicos de C#: la familiaridad con la programación de C# le ayudará a comprender mejor los fragmentos de código y los ejemplos.

4.  Documentación de Aspose.Words: consulte la[Documentación de Aspose.Words](https://reference.aspose.com/words/net/) para obtener información detallada sobre la API y lecturas adicionales.

## Importar espacios de nombres

Antes de comenzar a codificar, debe importar los espacios de nombres necesarios a su proyecto C#:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Estos espacios de nombres brindan acceso a las funcionalidades principales de Aspose.Words y el objeto Tabla, lo que le permite manipular tablas de documentos.

Dividamos el proceso de creación de una tabla con diferentes configuraciones de ancho preferidas en pasos claros y manejables.

## Paso 1: Inicialice el documento y DocumentBuilder

Título: Creación de un nuevo documento y DocumentBuilder

 Explicación: Comience creando un nuevo documento de Word y un`DocumentBuilder` instancia. El`DocumentBuilder` La clase proporciona una forma sencilla de agregar contenido a su documento.

```csharp
// Defina la ruta para guardar el documento.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crea un nuevo documento.
Document doc = new Document();

// Cree un DocumentBuilder para este documento.
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aquí, usted especifica el directorio donde se guardará el documento e inicializa el`Document`y`DocumentBuilder` objetos.

## Paso 2: inserte la primera celda de la tabla con ancho absoluto

Inserte la primera celda en la tabla con un ancho fijo de 40 puntos. Esto asegurará que esta celda siempre mantenga un ancho de 40 puntos independientemente del tamaño de la tabla.

```csharp

// Inserte una celda de tamaño absoluto.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell at 40 points width");
```

En este paso, comienzas a crear la tabla e insertas una celda con un ancho absoluto. El`PreferredWidth.FromPoints(40)` El método establece el ancho de la celda en 40 puntos y`Shading.BackgroundPatternColor` aplica un color de fondo amarillo claro.

## Paso 3: insertar una celda de tamaño relativo

Inserte otra celda con un ancho que sea el 20% del ancho total de la tabla. Este tamaño relativo garantiza que la celda se ajuste proporcionalmente al ancho de la tabla.

```csharp
// Inserte una celda de tamaño relativo (porcentaje).
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell at 20% width");
```

El ancho de esta celda será el 20% del ancho total de la tabla, lo que la hará adaptable a diferentes tamaños de pantalla o diseños de documentos.

### Paso 4: insertar una celda de tamaño automático

Finalmente, inserte una celda cuyo tamaño se ajuste automáticamente según el espacio disponible restante en la tabla.

```csharp
// Inserte una celda de tamaño automático.
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Cell automatically sized. The size of this cell is calculated from the table preferred width.");
builder.Writeln("In this case the cell will fill up the rest of the available space.");
```

 El`PreferredWidth.Auto` La configuración permite que esta celda se expanda o contraiga según el espacio que queda después de tener en cuenta las otras celdas. Esto garantiza que el diseño de la mesa luzca equilibrado y profesional.

## Paso 5: finalice y guarde el documento

Una vez que haya insertado todas sus celdas, complete la tabla y guarde el documento en la ruta especificada.

```csharp
// Guarde el documento.
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Este paso finaliza la tabla y guarda el documento con el nombre de archivo "WorkingWithTables.PreferredWidthSettings.docx" en su directorio designado.

## Conclusión

Crear tablas con la configuración de ancho preferida en Aspose.Words para .NET es sencillo una vez que comprende las diferentes opciones de tamaño disponibles. Ya sea que necesite anchos de celda fijos, relativos o automáticos, Aspose.Words brinda la flexibilidad para manejar varios escenarios de diseño de tablas de manera eficiente. Si sigue los pasos descritos en esta guía, podrá asegurarse de que sus tablas estén bien estructuradas y sean visualmente atractivas en sus documentos de Word.

## Preguntas frecuentes

### ¿Cuál es la diferencia entre anchos de celda absolutos y relativos?
Los anchos absolutos de celda son fijos y no cambian, mientras que los anchos relativos se ajustan según el ancho total de la tabla.

### ¿Puedo usar porcentajes negativos para anchos relativos?
No, los porcentajes negativos no son válidos para anchos de celda. Sólo se permiten porcentajes positivos.

### ¿Cómo funciona la función de tamaño automático?
El tamaño automático ajusta el ancho de la celda para llenar cualquier espacio restante en la tabla después de que se haya dimensionado otras celdas.

### ¿Puedo aplicar diferentes estilos a celdas con diferentes configuraciones de ancho?
Sí, puedes aplicar varios estilos y formatos a las celdas independientemente de su configuración de ancho.

### ¿Qué sucede si el ancho total de la tabla es menor que la suma de todos los anchos de las celdas?
La tabla ajustará automáticamente el ancho de las celdas para que quepan dentro del espacio disponible, lo que puede hacer que algunas celdas se reduzcan.