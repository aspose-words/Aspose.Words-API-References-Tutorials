---
title: Uso de propiedades de documento en Aspose.Words para Java
linktitle: Usar propiedades del documento
second_title: API de procesamiento de documentos Java Aspose.Words
description: Optimice la gestión de documentos con Aspose.Words para Java. Aprenda a trabajar con propiedades de documentos, agregue metadatos personalizados y más en este completo tutorial.
type: docs
weight: 32
url: /es/java/document-manipulation/using-document-properties/
---

## Introducción a las propiedades del documento

Las propiedades del documento son una parte vital de cualquier documento. Proporcionan información adicional sobre el documento en sí, como su título, autor, tema, palabras clave y más. En Aspose.Words para Java, puede manipular propiedades de documentos tanto integradas como personalizadas.

## Enumerar propiedades del documento

### Propiedades integradas

Para recuperar y trabajar con las propiedades integradas del documento, puede utilizar el siguiente fragmento de código:

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

Este código mostrará el nombre del documento y las propiedades integradas, incluidas propiedades como "Título", "Autor" y "Palabras clave".

### Propiedades personalizadas

Para trabajar con propiedades de documentos personalizadas, puede utilizar el siguiente fragmento de código:

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

Este fragmento de código demuestra cómo agregar propiedades de documento personalizadas, incluido un valor booleano, una cadena, una fecha, un número de revisión y un valor numérico.

## Eliminar propiedades del documento

Para eliminar propiedades específicas del documento, puede utilizar el siguiente código:

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

Este código elimina la propiedad personalizada "Fecha de autorización" del documento.

## Configurar enlace al contenido

En algunos casos, es posible que desee crear enlaces dentro de su documento. Así es como puedes hacerlo:

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    // Agregar propiedad vinculada al contenido.
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

Este fragmento de código demuestra cómo crear un marcador en su documento y agregar una propiedad de documento personalizada que se vincule a ese marcador.

## Conversión entre unidades de medida

En Aspose.Words para Java, puedes convertir unidades de medida fácilmente. Aquí tienes un ejemplo de cómo hacerlo:

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    // Establezca los márgenes en pulgadas.
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

Este fragmento de código establece varios márgenes y distancias en pulgadas convirtiéndolos en puntos.

## Usar caracteres de control

Los caracteres de control pueden resultar útiles cuando se trata de texto. A continuación se explica cómo reemplazar un carácter de control en su texto:

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    // Reemplace el carácter de control "\r" por "\r\n".
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

En este ejemplo, reemplazamos el retorno de carro (`\r`) con un retorno de carro seguido de un avance de línea (`\r\n`).

## Conclusión

Las propiedades de los documentos desempeñan un papel importante en la gestión y organización de sus documentos de forma eficaz en Aspose.Words para Java. Ya sea trabajando con propiedades integradas, propiedades personalizadas o usando caracteres de control, tiene una variedad de herramientas a su disposición para mejorar sus capacidades de administración de documentos.

## Preguntas frecuentes

### ¿Cómo accedo a las propiedades integradas del documento?

 Para acceder a las propiedades integradas del documento en Aspose.Words para Java, puede utilizar el`getBuiltInDocumentProperties` método en el`Document` objeto. Este método devuelve una colección de propiedades integradas que puede recorrer en iteración.

### ¿Puedo agregar propiedades de documento personalizadas a un documento?

 Sí, puede agregar propiedades de documento personalizadas a un documento usando el`CustomDocumentProperties` recopilación. Puede definir propiedades personalizadas con varios tipos de datos, incluidas cadenas, valores booleanos, fechas y valores numéricos.

### ¿Cómo puedo eliminar una propiedad de documento personalizada específica?

 Para eliminar una propiedad de documento personalizada específica, puede utilizar el`remove` método en el`CustomDocumentProperties`colección, pasando el nombre de la propiedad que desea eliminar como parámetro.

### ¿Cuál es el propósito de vincular al contenido dentro de un documento?

Vincular contenido dentro de un documento le permite crear referencias dinámicas a partes específicas del documento. Esto puede resultar útil para crear documentos interactivos o referencias cruzadas entre secciones.

### ¿Cómo puedo convertir entre diferentes unidades de medida en Aspose.Words para Java?

 Puede convertir entre diferentes unidades de medida en Aspose.Words para Java utilizando el`ConvertUtil` clase. Proporciona métodos para convertir unidades como pulgadas a puntos, puntos a centímetros y más.