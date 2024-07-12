---
title: Agregar contenido usando DocumentBuilder en Aspose.Words para Java
linktitle: Agregar contenido usando DocumentBuilder
second_title: API de procesamiento de documentos Java Aspose.Words
description: Creación de documentos maestros con Aspose.Words para Java. Una guía paso a paso para agregar texto, tablas, imágenes y más. Cree impresionantes documentos de Word sin esfuerzo.
type: docs
weight: 26
url: /es/java/document-manipulation/adding-content-using-documentbuilder/
---

## Introducción a agregar contenido usando DocumentBuilder en Aspose.Words para Java

En esta guía paso a paso, exploraremos cómo usar Aspose.Words para DocumentBuilder de Java para agregar varios tipos de contenido a un documento de Word. Cubriremos la inserción de texto, tablas, reglas horizontales, campos de formulario, HTML, hipervínculos, tabla de contenido, imágenes flotantes y en línea, párrafos y más. ¡Empecemos!

## Requisitos previos

 Antes de comenzar, asegúrese de tener la biblioteca Aspose.Words para Java configurada en su proyecto. Puedes descargarlo desde[aquí](https://releases.aspose.com/words/java/).

## Agregar texto

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar un párrafo de texto simple
builder.write("This is a simple text paragraph.");

// guardar el documento
doc.save("path/to/your/document.docx");
```

## Agregar tablas

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// iniciar una mesa
Table table = builder.startTable();

// Insertar celdas y contenido
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// terminar la mesa
builder.endTable();

// guardar el documento
doc.save("path/to/your/document.docx");
```

## Agregar regla horizontal

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar una regla horizontal
builder.insertHorizontalRule();

// guardar el documento
doc.save("path/to/your/document.docx");
```

## Agregar campos de formulario

### Campo de formulario de entrada de texto

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar un campo de formulario de entrada de texto
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// guardar el documento
doc.save("path/to/your/document.docx");
```

### Campo de formulario de casilla de verificación

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar un campo de formulario de casilla de verificación
builder.insertCheckBox("CheckBox", true, true, 0);

// guardar el documento
doc.save("path/to/your/document.docx");
```

### Campo de formulario de cuadro combinado

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Definir elementos para el cuadro combinado
String[] items = { "Option 1", "Option 2", "Option 3" };

// Insertar un campo de formulario de cuadro combinado
builder.insertComboBox("DropDown", items, 0);

// guardar el documento
doc.save("path/to/your/document.docx");
```

## Agregar HTML

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar contenido HTML
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// guardar el documento
doc.save("path/to/your/document.docx");
```

## Agregar hipervínculos

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar un hipervínculo
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com", falso);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// guardar el documento
doc.save("path/to/your/document.docx");
```

## Agregar una tabla de contenido

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar una tabla de contenido
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Agregar contenido al documento
// ...

// Actualizar la tabla de contenidos
doc.updateFields();

// guardar el documento
doc.save("path/to/your/document.docx");
```

## Agregar imágenes

### Imagen en línea

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar una imagen en línea
builder.insertImage("path/to/your/image.png");

// guardar el documento
doc.save("path/to/your/document.docx");
```

### Imagen flotante

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar una imagen flotante
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// guardar el documento
doc.save("path/to/your/document.docx");
```

## Agregar párrafos

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Establecer formato de párrafo
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Insertar un párrafo
builder.writeln("This is a formatted paragraph.");

// guardar el documento
doc.save("path/to/your/document.docx");
```

## Paso 10: mover el cursor

 Puede controlar la posición del cursor dentro del documento utilizando varios métodos como`moveToParagraph`, `moveToCell`y más. He aquí un ejemplo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Mover el cursor a un párrafo específico
builder.moveToParagraph(2, 0);

// Agregar contenido en la nueva posición del cursor
builder.writeln("This is the 3rd paragraph.");
```

Estas son algunas operaciones comunes que puede realizar utilizando Aspose.Words para DocumentBuilder de Java. Explore la documentación de la biblioteca para conocer funciones más avanzadas y opciones de personalización. ¡Feliz creación de documentos!


## Conclusión

En esta guía completa, hemos explorado las capacidades de Aspose.Words para DocumentBuilder de Java para agregar varios tipos de contenido a documentos de Word. Hemos cubierto texto, tablas, reglas horizontales, campos de formulario, HTML, hipervínculos, tabla de contenido, imágenes, párrafos y movimiento del cursor.

## Preguntas frecuentes

### P: ¿Qué es Aspose.Words para Java?

R: Aspose.Words para Java es una biblioteca de Java que permite a los desarrolladores crear, modificar y manipular documentos de Microsoft Word mediante programación. Proporciona una amplia gama de funciones para la generación, el formato y la inserción de contenido de documentos.

### P: ¿Cómo puedo agregar una tabla de contenido a mi documento?

R: Para agregar una tabla de contenido, use el`DocumentBuilder` para insertar un campo de tabla de contenido en su documento. Asegúrese de actualizar los campos del documento después de agregar contenido para completar la tabla de contenido. He aquí un ejemplo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar un campo de tabla de contenido
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Agregar contenido al documento
// ...

// Actualizar la tabla de contenidos
doc.updateFields();
```

### P: ¿Cómo inserto imágenes en un documento usando Aspose.Words para Java?

 R: Puedes insertar imágenes, tanto en línea como flotantes, usando el`DocumentBuilder`. A continuación se muestran ejemplos de ambos:

#### Imagen en línea:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar una imagen en línea
builder.insertImage("path/to/your/image.png");
```

#### Imagen flotante:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar una imagen flotante
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### P: ¿Puedo formatear texto y párrafos al agregar contenido?

 R: Sí, puedes formatear texto y párrafos usando el`DocumentBuilder`. Puede configurar propiedades de fuente, alineación de párrafos, sangría y más. He aquí un ejemplo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Establecer formato de fuente y párrafo
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Insertar un párrafo formateado
builder.writeln("This is a formatted paragraph.");
```

### P: ¿Cómo puedo mover el cursor a una ubicación específica dentro del documento?

 R: Puedes controlar la posición del cursor usando métodos como`moveToParagraph`, `moveToCell`y más. He aquí un ejemplo:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Mover el cursor a un párrafo específico
builder.moveToParagraph(2, 0);

// Agregar contenido en la nueva posición del cursor
builder.writeln("This is the 3rd paragraph.");
```

Estas son algunas preguntas y respuestas comunes que le ayudarán a empezar a utilizar Aspose.Words para DocumentBuilder de Java. Si tiene más preguntas o necesita más ayuda, consulte la[documentación de la biblioteca](https://reference.aspose.com/words/java/) o busque ayuda de la comunidad Aspose.Words y recursos de soporte.