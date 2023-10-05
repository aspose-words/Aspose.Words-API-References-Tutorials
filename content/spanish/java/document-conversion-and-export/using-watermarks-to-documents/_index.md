---
title: Uso de marcas de agua en documentos en Aspose.Words para Java
linktitle: Usar marcas de agua en documentos
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda cómo agregar marcas de agua a documentos en Aspose.Words para Java. Personalice marcas de agua de texto e imágenes para documentos de aspecto profesional.
type: docs
weight: 15
url: /es/java/document-conversion-and-export/using-watermarks-to-documents/
---

## Introducción a la adición de marcas de agua a documentos en Aspose.Words para Java

En este tutorial, exploraremos cómo agregar marcas de agua a documentos usando la API Aspose.Words para Java. Las marcas de agua son una forma útil de etiquetar documentos con texto o gráficos para indicar su estado, confidencialidad u otra información relevante. En esta guía cubriremos marcas de agua de texto e imagen.

## Configurando Aspose.Words para Java

Antes de comenzar a agregar marcas de agua a los documentos, debemos configurar Aspose.Words para Java. Siga estos pasos para comenzar:

1.  Descargue Aspose.Words para Java desde[aquí](https://releases.aspose.com/words/java/).
2. Agregue la biblioteca Aspose.Words para Java a su proyecto Java.
3. Importe las clases necesarias en su código Java.

Ahora que tenemos la biblioteca configurada, procedamos a agregar marcas de agua.

## Agregar marcas de agua de texto

Las marcas de agua de texto son una opción común cuando desea agregar información textual a sus documentos. Así es como puedes agregar una marca de agua de texto usando Aspose.Words para Java:

```java
//Crear una instancia de documento
Document doc = new Document("Document.docx");

// Definir opciones de marca de agua de texto
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// Establecer el texto y las opciones de la marca de agua
doc.getWatermark().setText("Test", options);

// Guarde el documento con la marca de agua.
doc.save("DocumentWithWatermark.docx");
```

## Agregar marcas de agua de imagen

Además de las marcas de agua de texto, también puede agregar marcas de agua de imágenes a sus documentos. A continuación se explica cómo agregar una marca de agua de imagen:

```java
//Crear una instancia de documento
Document doc = new Document("Document.docx");

// Cargue la imagen para la marca de agua.
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// Establecer el tamaño y la posición de la marca de agua
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// Agregar la marca de agua al documento.
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Guarde el documento con la marca de agua.
doc.save("DocumentWithImageWatermark.docx");
```

## Personalización de marcas de agua

Puede personalizar las marcas de agua ajustando su apariencia y posición. Para las marcas de agua de texto, puede cambiar la fuente, el tamaño, el color y el diseño. Para marcas de agua de imágenes, puede modificar su tamaño y posición como se demuestra en los ejemplos anteriores.

## Eliminar marcas de agua

Para eliminar marcas de agua de un documento, puede utilizar el siguiente código:

```java
//Crear una instancia de documento
Document doc = new Document("DocumentWithWatermark.docx");

// Quitar la marca de agua
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// Guarde el documento sin la marca de agua.
doc.save("DocumentWithoutWatermark.docx");
```


## Conclusión

En este tutorial, aprendimos cómo agregar marcas de agua a documentos usando Aspose.Words para Java. Ya sea que necesite agregar marcas de agua de texto o imágenes, Aspose.Words proporciona las herramientas para personalizarlas y administrarlas de manera eficiente. También puede eliminar marcas de agua cuando ya no sean necesarias, asegurando que sus documentos estén limpios y profesionales.

## Preguntas frecuentes

### ¿Cómo puedo cambiar la fuente de una marca de agua de texto?

 Para cambiar la fuente de una marca de agua de texto, modifique el`setFontFamily` propiedad en el`TextWatermarkOptions`. Por ejemplo:

```java
options.setFontFamily("Times New Roman");
```

### ¿Puedo agregar varias marcas de agua a un solo documento?

 Sí, puede agregar varias marcas de agua a un documento creando varias`Shape` objetos con diferentes configuraciones y agregarlos al documento.

### ¿Es posible rotar una marca de agua?

 Sí, puedes rotar una marca de agua configurando el`setRotation` propiedad en el`Shape` objeto. Los valores positivos giran la marca de agua en el sentido de las agujas del reloj y los valores negativos la giran en el sentido contrario a las agujas del reloj.

### ¿Cómo puedo hacer que una marca de agua sea semitransparente?

 Para hacer una marca de agua semitransparente, configure el`setSemitransparent`propiedad a`true` en el`TextWatermarkOptions`.

### ¿Puedo agregar marcas de agua a secciones específicas de un documento?

Sí, puede agregar marcas de agua a secciones específicas de un documento recorriendo las secciones y agregando la marca de agua a las secciones deseadas.