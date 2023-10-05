---
title: Formato de tablas y estilos de tablas en Aspose.Words para Java
linktitle: Dar formato a tablas y estilos de tabla
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a formatear tablas y aplicar estilos de tabla en Aspose.Words para Java. Explore guías paso a paso con código fuente para formatear tablas de manera eficaz. Mejore el diseño de su documento con Aspose.Words.
type: docs
weight: 17
url: /es/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Introducción al formato de tablas y estilos de tablas en Aspose.Words para Java

Las tablas juegan un papel crucial en la estructuración y organización de la información en los documentos. Aspose.Words para Java proporciona potentes funciones para formatear tablas y aplicar estilos de tabla para mejorar el atractivo visual de sus documentos. En esta guía paso a paso, exploraremos varios aspectos del formato de tablas y la aplicación de estilos de tabla usando Aspose.Words para Java.

## Requisitos previos

Antes de profundizar en los detalles, asegúrese de tener la biblioteca Aspose.Words para Java integrada en su proyecto. Puedes descargarlo desde el sitio web de Aspose:[Descargar Aspose.Words para Java](https://releases.aspose.com/words/java/).

## Obtener la distancia entre la tabla y el texto circundante

Para comenzar, exploremos cómo recuperar la distancia entre una tabla y el texto circundante en un documento.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Aplicar borde de contorno a una tabla

Puede alinear una tabla con el centro de la página, borrar los bordes existentes y establecer un borde de contorno personalizado con este código:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## Construir una mesa con bordes

Este fragmento de código demuestra cómo crear una tabla y establecer bordes tanto para la tabla como para sus celdas:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Modificar el formato de fila

Aprenda a modificar el formato de una fila específica dentro de una tabla:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Aplicar formato de fila

Este ejemplo demuestra cómo aplicar formato a una fila completa en una tabla:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Establecer relleno de celda

Explore cómo configurar el relleno para celdas individuales en una tabla:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Modificar el formato de celda

Descubra cómo modificar el formato de una celda específica dentro de una tabla:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Formatear tabla y celda con diferentes bordes

Aprenda a establecer diferentes bordes para celdas individuales en una tabla:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Establecer los bordes de la mesa
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Establecer sombreado de celdas para celdas individuales
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Agregar contenido a las celdas
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Borrar formato de celda para la siguiente fila
builder.getCellFormat().clearFormatting();
// Crea bordes más grandes para la primera celda de esta fila
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Establecer título y descripción de la tabla

Añade un título y una descripción a tu tabla:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Paso 10: permitir el espacio entre celdas

Permita el espaciado de celdas y establezca su valor para una tabla:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Paso 11: construye una mesa con estilo

Crea una tabla con un estilo predefinido:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Paso 12: expanda el formato en celdas y filas desde Estilo

Aprenda a expandir los estilos de tabla para aplicar formato a celdas y filas:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Paso 13: crea un estilo de tabla

Cree un estilo de tabla personalizado con formato específico:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Paso 14: Definir el formato condicional

Aplique formato condicional a las filas de una tabla:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Paso 15: configurar el formato de TableCell

Establezca un formato específico para celdas individuales:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Paso 16: Establecer el formato TableRow

Aplicar formato a filas enteras de una tabla:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Conclusión

Aspose.Words para Java le permite formatear tablas y aplicar estilos de tabla con precisión. Desde modificar el formato de celdas individuales hasta crear estilos de tabla personalizados, tiene las herramientas para hacer que sus documentos sean visualmente atractivos y organizados.

## Preguntas frecuentes

### ¿Cómo descargo Aspose.Words para Java?

 Puede descargar Aspose.Words para Java desde el sitio web de Aspose:[Descargar Aspose.Words para Java](https://releases.aspose.com/words/java/).

### ¿Puedo aplicar diferentes bordes a celdas individuales dentro de una tabla?

Sí, puedes establecer diferentes bordes para celdas individuales dentro de una tabla usando Aspose.Words para Java, como se demuestra en esta guía.

### ¿Cuál es el propósito de establecer un título y una descripción de la tabla?

Establecer un título y una descripción de la tabla mejora la accesibilidad y la organización de su documento, lo que facilita que los lectores y las tecnologías de asistencia comprendan el contenido.

### ¿Cómo puedo aplicar formato condicional a filas específicas de una tabla?

Puede aplicar formato condicional a filas específicas de una tabla definiendo estilos de tabla personalizados con reglas de formato condicional, como se muestra en esta guía.

### ¿Dónde puedo encontrar más documentación y recursos para Aspose.Words para Java?

 Para obtener documentación completa y recursos adicionales, visite la documentación de Aspose.Words para Java:[Aspose.Words para la documentación de Java](https://reference.aspose.com/words/java/).