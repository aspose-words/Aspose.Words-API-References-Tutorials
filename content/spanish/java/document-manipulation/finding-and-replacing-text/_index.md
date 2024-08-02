---
title: Buscar y reemplazar texto en Aspose.Words para Java
linktitle: Buscar y reemplazar texto
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a buscar y reemplazar texto en documentos de Word con Aspose.Words para Java. Guía paso a paso con ejemplos de código. Mejore sus habilidades de manipulación de documentos Java.
type: docs
weight: 15
url: /es/java/document-manipulation/finding-and-replacing-text/
---

## Introducción a buscar y reemplazar texto en Aspose.Words para Java

Aspose.Words para Java es una potente API de Java que le permite trabajar con documentos de Word mediante programación. Una de las tareas comunes cuando se trabaja con documentos de Word es buscar y reemplazar texto. Ya sea que necesite actualizar marcadores de posición en plantillas o realizar manipulaciones de texto más complejas, Aspose.Words para Java puede ayudarlo a lograr sus objetivos de manera eficiente.

## Requisitos previos

Antes de profundizar en los detalles de cómo buscar y reemplazar texto, asegúrese de cumplir con los siguientes requisitos previos:

- Entorno de desarrollo Java
- Biblioteca Aspose.Words para Java
- Un documento de Word de muestra para trabajar

 Puede descargar la biblioteca Aspose.Words para Java desde[aquí](https://releases.aspose.com/words/java/).

## Buscar y reemplazar texto simple

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Crear un generador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);

// Buscar y reemplazar texto
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Guardar el documento modificado
doc.save("modified-document.docx");
```

 En este ejemplo, cargamos un documento de Word, creamos un`DocumentBuilder` y utilizar el`replace` Método para buscar y reemplazar "texto antiguo" con "texto nuevo" dentro del documento.

## Usando expresiones regulares

Las expresiones regulares proporcionan poderosas capacidades de coincidencia de patrones para la búsqueda y reemplazo de texto. Aspose.Words para Java admite expresiones regulares para operaciones de búsqueda y reemplazo más avanzadas.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Crear un generador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);

// Utilice expresiones regulares para buscar y reemplazar texto
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Guardar el documento modificado
doc.save("modified-document.docx");
```

En este ejemplo, utilizamos un patrón de expresión regular para buscar y reemplazar texto dentro del documento.

## Ignorar el texto dentro de los campos

Puede configurar Aspose.Words para ignorar el texto dentro de los campos al realizar operaciones de búsqueda y reemplazo.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Cree una instancia de FindReplaceOptions y establezca IgnoreFields en verdadero
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Usar opciones al reemplazar texto
doc.getRange().replace("text-to-replace", "new-text", options);

// Guardar el documento modificado
doc.save("modified-document.docx");
```

Esto es útil cuando desea excluir el texto dentro de campos, como campos de combinación, para que no se reemplace.

## Ignorar el texto dentro de las revisiones de eliminación

Puede configurar Aspose.Words para ignorar el texto dentro de las revisiones de eliminación durante las operaciones de búsqueda y reemplazo.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Cree una instancia de FindReplaceOptions y establezca IgnoreDeleted en verdadero
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Usar opciones al reemplazar texto
doc.getRange().replace("text-to-replace", "new-text", options);

// Guardar el documento modificado
doc.save("modified-document.docx");
```

Esto le permite excluir el texto que se ha marcado para su eliminación en los cambios registrados para que no se reemplace.

## Ignorar el texto dentro de las revisiones de inserción

Puede configurar Aspose.Words para ignorar el texto dentro de las revisiones de inserción durante las operaciones de búsqueda y reemplazo.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Cree una instancia de FindReplaceOptions y establezca IgnoreInserted en verdadero
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Usar opciones al reemplazar texto
doc.getRange().replace("text-to-replace", "new-text", options);

// Guardar el documento modificado
doc.save("modified-document.docx");
```

Esto le permite excluir el texto que se ha marcado como insertado en los cambios registrados para que no se reemplace.

## Reemplazo de texto con HTML

Puede utilizar Aspose.Words para Java para reemplazar texto con contenido HTML.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Cree una instancia de FindReplaceOptions con una devolución de llamada de reemplazo personalizada
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Usar opciones al reemplazar texto
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Guardar el documento modificado
doc.save("modified-document.docx");
```

 En este ejemplo, utilizamos una costumbre`ReplaceWithHtmlEvaluator` para reemplazar texto con contenido HTML.

## Reemplazo de texto en encabezados y pies de página

Puede buscar y reemplazar texto en los encabezados y pies de página de su documento de Word.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Obtenga la colección de encabezados y pies de página
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Elija el tipo de encabezado o pie de página en el que desea reemplazar el texto (por ejemplo, HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Cree una instancia de FindReplaceOptions y aplíquela al rango del pie de página
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Guardar el documento modificado
doc.save("modified-document.docx");
```

Esto le permite realizar reemplazos de texto específicamente en encabezados y pies de página.

## Mostrar cambios para pedidos de encabezado y pie de página

Puede utilizar Aspose.Words para mostrar cambios en los pedidos de encabezado y pie de página en su documento.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Obtener la primera sección
Section firstPageSection = doc.getFirstSection();

// Cree una instancia de FindReplaceOptions y aplíquela al rango del documento
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//Reemplazar texto que afecta el orden del encabezado y pie de página
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Guardar el documento modificado
doc.save("modified-document.docx");
```

Esto le permite visualizar cambios relacionados con los pedidos de encabezado y pie de página en su documento.

## Reemplazo de texto con campos

Puede reemplazar texto con campos usando Aspose.Words para Java.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Cree una instancia de FindReplaceOptions y establezca una devolución de llamada de reemplazo personalizada para los campos
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Usar opciones al reemplazar texto
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Guardar el documento modificado
doc.save("modified-document.docx");
```

 En este ejemplo, reemplazamos el texto con campos y especificamos el tipo de campo (p. ej.,`FieldType.FIELD_MERGE_FIELD`).

## Reemplazo con un evaluador

Puede utilizar un evaluador personalizado para determinar el texto de reemplazo de forma dinámica.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Cree una instancia de FindReplaceOptions y establezca una devolución de llamada de reemplazo personalizada
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Usar opciones al reemplazar texto
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Guardar el documento modificado
doc.save("modified-document.docx");
```

En este ejemplo, utilizamos un evaluador personalizado (`MyReplaceEvaluator`) para reemplazar el texto.

## Reemplazo con expresiones regulares

Aspose.Words para Java le permite reemplazar texto usando expresiones regulares.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Utilice expresiones regulares para buscar y reemplazar texto
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Guardar el documento modificado
doc.save("modified-document.docx");
```

En este ejemplo, utilizamos un patrón de expresión regular para buscar y reemplazar texto dentro del documento.

## Reconocimiento y sustituciones dentro de patrones de reemplazo

Puede reconocer y realizar sustituciones dentro de patrones de reemplazo utilizando Aspose.Words para Java.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

//Cree una instancia de FindReplaceOptions con UseSubstitutions establecido en verdadero
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Usar opciones al reemplazar texto con un patrón
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Guardar el documento modificado
doc.save("modified-document.docx");
```

Esto le permite realizar sustituciones dentro de los patrones de reemplazo para reemplazos más avanzados.

## Reemplazo con una cuerda

Puede reemplazar texto con una cadena simple usando Aspose.Words para Java.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Reemplazar texto con una cadena
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Guardar el documento modificado
doc.save("modified-document.docx");
```

En este ejemplo, reemplazamos "texto para reemplazar" con "nueva cadena" dentro del documento.

## Usando orden heredada

Puede utilizar el orden heredado al realizar operaciones de búsqueda y reemplazo.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Cree una instancia de FindReplaceOptions y establezca UseLegacyOrder en verdadero
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Usar opciones al reemplazar texto
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Guardar el documento modificado
doc.save("modified-document.docx");
```

Esto le permite utilizar el orden heredado para operaciones de búsqueda y reemplazo.

## Reemplazo de texto en una tabla

Puede buscar y reemplazar texto dentro de las tablas de su documento de Word.

```java
// Cargar el documento
Document doc = new Document("your-document.docx");

// Obtener una tabla específica (por ejemplo, la primera tabla)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// Utilice FindReplaceOptions para reemplazar texto en la tabla
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Guardar el documento modificado
doc.save("modified-document.docx");
```

Esto le permite realizar reemplazos de texto específicamente dentro de tablas.

## Conclusión

Aspose.Words para Java proporciona capacidades integrales para buscar y reemplazar texto dentro de documentos de Word. Ya sea que necesite realizar reemplazos de texto simples u operaciones más avanzadas usando expresiones regulares, manipulaciones de campos o evaluadores personalizados, Aspose.Words para Java lo tiene cubierto. Asegúrese de explorar la extensa documentación y los ejemplos proporcionados por Aspose para aprovechar todo el potencial de esta poderosa biblioteca de Java.

## Preguntas frecuentes

### ¿Cómo descargo Aspose.Words para Java?

 Puede descargar Aspose.Words para Java desde el sitio web visitando[este enlace](https://releases.aspose.com/words/java/).

### ¿Puedo usar expresiones regulares para reemplazar texto?

Sí, puede utilizar expresiones regulares para reemplazar texto en Aspose.Words para Java. Esto le permite realizar operaciones de búsqueda y reemplazo más avanzadas y flexibles.

### ¿Cómo puedo ignorar el texto dentro de los campos durante el reemplazo?

 Para ignorar el texto dentro de los campos durante el reemplazo, puede configurar el`IgnoreFields` propiedad de la`FindReplaceOptions` a`true`Esto garantiza que el texto dentro de los campos, como los campos de combinación, quede excluido del reemplazo.

### ¿Puedo reemplazar el texto dentro de los encabezados y pies de página?

 Sí, puedes reemplazar el texto dentro de los encabezados y pies de página de tu documento de Word. Simplemente acceda al encabezado o pie de página correspondiente y utilice el`replace` método con el deseado`FindReplaceOptions`.

### ¿Para qué sirve la opción UseLegacyOrder?

 El`UseLegacyOrder` opción en`FindReplaceOptions` le permite utilizar el orden heredado al realizar operaciones de búsqueda y reemplazo. Esto puede resultar útil en determinados escenarios en los que se desea un comportamiento de orden heredado.