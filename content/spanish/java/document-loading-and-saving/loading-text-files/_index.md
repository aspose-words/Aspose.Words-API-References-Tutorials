---
title: Cargando archivos de texto con Aspose.Words para Java
linktitle: Cargando archivos de texto con
second_title: API de procesamiento de documentos Java Aspose.Words
description: Desbloquee el poder de Aspose.Words para Java. Aprenda a cargar documentos de texto, administrar listas, manejar espacios y controlar la dirección del texto.
type: docs
weight: 13
url: /es/java/document-loading-and-saving/loading-text-files/
---

## Introducción a la carga de archivos de texto con Aspose.Words para Java

En esta guía, exploraremos cómo cargar archivos de texto usando Aspose.Words para Java y manipularlos como documentos de Word. Cubriremos varios aspectos como la detección de listas, el manejo de espacios y el control de la dirección del texto.

## Paso 1: detectar listas

Para cargar un documento de texto y detectar listas, puede seguir estos pasos:

```java
// Cree un documento de texto sin formato en forma de cadena con partes que puedan interpretarse como listas.
// Al cargar, Aspose.Words siempre detectará las tres primeras listas,
// y los objetos de lista se crearán para ellos después de la carga.
final String TEXT_DOC = "Full stop delimiters:\n" +
        "1. First list item 1\n" +
        "2. First list item 2\n" +
        "3. First list item 3\n\n" +
        "Right bracket delimiters:\n" +
        "1) Second list item 1\n" +
        "2) Second list item 2\n" +
        "3) Second list item 3\n\n" +
        "Bullet delimiters:\n" +
        "• Third list item 1\n" +
        "• Third list item 2\n" +
        "• Third list item 3\n\n" +
        "Whitespace delimiters:\n" +
        "1 Fourth list item 1\n" +
        "2 Fourth list item 2\n" +
        "3 Fourth list item 3";
//La cuarta lista, con espacios en blanco entre el número de la lista y el contenido del elemento de la lista,
// solo se detectará como una lista si "DetectNumberingWithWhitespaces" en un objeto LoadOptions está establecido en verdadero,
// para evitar que los párrafos que comienzan con números se detecten erróneamente como listas.
TxtLoadOptions loadOptions = new TxtLoadOptions();
{
    loadOptions.setDetectNumberingWithWhitespaces(true);
}
// Cargue el documento mientras aplica LoadOptions como parámetro y verifique el resultado.
Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Este código demuestra cómo cargar un documento de texto con varios formatos de lista y usar el`DetectNumberingWithWhitespaces` opción para detectar listas correctamente.

## Paso 2: Manejo de las opciones de espacios

Para controlar los espacios iniciales y finales al cargar un documento de texto, puede utilizar el siguiente código:

```java
@Test
public void handleSpacesOptions() throws Exception {
    final String TEXT_DOC = "      Line 1 \n" +
            "    Line 2   \n" +
            " Line 3       ";
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
        loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
    }
    Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
```

 En este ejemplo, cargamos un documento de texto y recortamos los espacios iniciales y finales usando`TxtLeadingSpacesOptions.TRIM` y`TxtTrailingSpacesOptions.TRIM`.

## Paso 3: controlar la dirección del texto

Para especificar la dirección del texto al cargar un documento de texto, puede utilizar el siguiente código:

```java
@Test
public void documentTextDirection() throws Exception {
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setDocumentDirection(DocumentDirection.AUTO);
    }
    Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
    Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
    System.out.println(paragraph.getParagraphFormat().getBidi());
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
}
```

Este código establece la dirección del documento en detección automática (`DocumentDirection.AUTO`y carga un documento de texto con texto hebreo. Puede ajustar la dirección del documento según sea necesario.

## Código fuente completo para cargar archivos de texto con Aspose.Words para Java

```java
public void detectNumberingWithWhitespaces() throws Exception {
	// Cree un documento de texto sin formato en forma de cadena con partes que puedan interpretarse como listas.
	// Al cargar, Aspose.Words siempre detectará las tres primeras listas,
	// y los objetos de lista se crearán para ellos después de la carga.
	final String TEXT_DOC = "Full stop delimiters:\n" +
			"1. First list item 1\n" +
			"2. First list item 2\n" +
			"3. First list item 3\n\n" +
			"Right bracket delimiters:\n" +
			"1) Second list item 1\n" +
			"2) Second list item 2\n" +
			"3) Second list item 3\n\n" +
			"Bullet delimiters:\n" +
			"• Third list item 1\n" +
			"• Third list item 2\n" +
			"• Third list item 3\n\n" +
			"Whitespace delimiters:\n" +
			"1 Fourth list item 1\n" +
			"2 Fourth list item 2\n" +
			"3 Fourth list item 3";
	// La cuarta lista, con espacios en blanco entre el número de la lista y el contenido del elemento de la lista,
	// solo se detectará como una lista si "DetectNumberingWithWhitespaces" en un objeto LoadOptions está establecido en verdadero,
	// para evitar que los párrafos que comienzan con números se detecten erróneamente como listas.
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDetectNumberingWithWhitespaces(true);
	}
	// Cargue el documento mientras aplica LoadOptions como parámetro y verifique el resultado.
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
}
@Test
public void handleSpacesOptions() throws Exception {
	final String TEXT_DOC = "      Line 1 \n" +
			"    Line 2   \n" +
			" Line 3       ";
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
		loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
	}
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
@Test
public void documentTextDirection() throws Exception {
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDocumentDirection(DocumentDirection.AUTO);
	}
	Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
	Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
	System.out.println(paragraph.getParagraphFormat().getBidi());
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
	}
```

## Conclusión

En esta guía, exploramos cómo cargar archivos de texto usando Aspose.Words para Java, detectar listas, manejar espacios y controlar la dirección del texto. Estas técnicas le permiten manipular documentos de texto de forma eficaz en sus aplicaciones Java.

## Preguntas frecuentes

### ¿Qué es Aspose.Words para Java?

Aspose.Words para Java es una potente biblioteca de procesamiento de documentos que permite a los desarrolladores crear, manipular y convertir documentos de Word mediante programación en aplicaciones Java. Proporciona una amplia gama de funciones para trabajar con texto, tablas, imágenes y otros elementos del documento.

### ¿Cómo puedo empezar con Aspose.Words para Java?

Para comenzar con Aspose.Words para Java, siga estos pasos:
1. Descargue e instale la biblioteca Aspose.Words para Java.
2.  Consulte la documentación en[Referencia de la API de Aspose.Words para Java](https://reference.aspose.com/words/java/)para obtener información detallada y ejemplos.
3. Explore el código de muestra y los tutoriales para aprender a utilizar la biblioteca de forma eficaz.

### ¿Cómo cargo un documento de texto usando Aspose.Words para Java?

 Para cargar un documento de texto usando Aspose.Words para Java, puede usar el`TxtLoadOptions` clase y el`Document` clase. Asegúrese de especificar las opciones adecuadas para manejar espacios y dirección del texto según sea necesario. Consulte la guía paso a paso de este artículo para ver un ejemplo detallado.

### ¿Puedo convertir un documento de texto cargado a otros formatos?

 Sí, Aspose.Words para Java le permite convertir un documento de texto cargado a varios formatos, incluidos DOCX, PDF y más. Puedes usar el`Document` clase para realizar conversiones. Consulte la documentación para ver ejemplos de conversión específicos.

### ¿Cómo manejo los espacios en documentos de texto cargados?

 Puede controlar cómo se manejan los espacios iniciales y finales en documentos de texto cargados usando`TxtLoadOptions` . Opciones como`TxtLeadingSpacesOptions` y`TxtTrailingSpacesOptions`Le permite recortar o preservar espacios según sea necesario. Consulte la sección "Opciones de manejo de espacios" de esta guía para ver un ejemplo.

### ¿Cuál es el significado de la dirección del texto en Aspose.Words para Java?

La dirección del texto es esencial para documentos que contienen escrituras o idiomas mixtos, como el hebreo o el árabe. Aspose.Words para Java proporciona opciones para especificar la dirección del texto, lo que garantiza una representación y formato adecuados del texto en estos idiomas. La sección "Control de la dirección del texto" de esta guía muestra cómo configurar la dirección del texto.

### ¿Dónde puedo encontrar más recursos y soporte para Aspose.Words para Java?

 Para obtener recursos, documentación y soporte adicionales, visite el[Aspose.Words para la documentación de Java](https://reference.aspose.com/words/java/). También puede participar en los foros de la comunidad Aspose.Words o comunicarse con el soporte de Aspose para obtener ayuda con problemas o consultas específicas.

### ¿Aspose.Words para Java es adecuado para proyectos comerciales?

Sí, Aspose.Words para Java es adecuado tanto para proyectos personales como comerciales. Ofrece opciones de licencia para adaptarse a diversos escenarios de uso. Asegúrese de revisar los términos de la licencia y los precios en el sitio web de Aspose para elegir la licencia adecuada para su proyecto.