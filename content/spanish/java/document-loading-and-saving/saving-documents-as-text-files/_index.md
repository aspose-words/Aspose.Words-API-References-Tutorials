---
title: Guardar documentos como archivos de texto en Aspose.Words para Java
linktitle: Guardar documentos como archivos de texto
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a guardar documentos como archivos de texto en Aspose.Words para Java. Siga nuestra guía paso a paso con ejemplos de código Java.
type: docs
weight: 24
url: /es/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Introducción a guardar documentos como archivos de texto en Aspose.Words para Java

En este tutorial, exploraremos cómo guardar documentos como archivos de texto usando la biblioteca Aspose.Words para Java. Aspose.Words es una potente API de Java para trabajar con documentos de Word y proporciona varias opciones para guardar documentos en diferentes formatos, incluido el texto sin formato. Cubriremos los pasos para lograr esto y proporcionaremos código Java de muestra a lo largo del camino.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Kit de desarrollo de Java (JDK) instalado en su sistema.
-  Biblioteca Aspose.Words para Java integrada en su proyecto. Puedes descargarlo desde[aquí](https://releases.aspose.com/words/java/).
- Conocimientos básicos de programación Java.

## Paso 1: crear un documento

Para guardar un documento como un archivo de texto, primero debemos crear un documento usando Aspose.Words. Aquí hay un fragmento de código Java simple para crear un documento con algún contenido:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

En este código, creamos un nuevo documento y le agregamos algo de texto, incluido texto en diferentes idiomas.

## Paso 2: definir las opciones para guardar texto

A continuación, debemos definir las opciones para guardar texto que especifican cómo se debe guardar el documento como archivo de texto. Podemos configurar varios ajustes como agregar marcas bidi, sangría de lista y más. Veamos dos ejemplos:

### Ejemplo 1: agregar marcas Bidi

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 En este ejemplo, creamos un`TxtSaveOptions` objeto y establecer el`AddBidiMarks`propiedad a`true` para incluir marcas bidi en la salida del texto.

### Ejemplo 2: uso del carácter de tabulación para sangría de lista

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Aquí, configuramos las opciones de guardar para usar un carácter de tabulación para la sangría de la lista con un recuento de 1.

## Paso 3: guarde el documento como texto

Ahora que hemos definido las opciones para guardar texto, podemos guardar el documento como un archivo de texto. El siguiente código demuestra cómo hacer esto:

```java
doc.save("output.txt", saveOptions);
```

 Reemplazar`"output.txt"` con la ruta del archivo deseado donde desea guardar el archivo de texto.

## Código fuente completo para guardar documentos como archivos de texto en Aspose.Words para Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crea una lista con tres niveles de sangría.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crea una lista con tres niveles de sangría.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## Conclusión

En este tutorial, aprendimos cómo guardar documentos como archivos de texto en Aspose.Words para Java. Cubrimos los pasos para crear un documento, definir opciones para guardar texto y guardar el documento en formato de texto. Aspose.Words proporciona una gran flexibilidad a la hora de guardar documentos, lo que le permite adaptar la salida a sus necesidades específicas.

## Preguntas frecuentes

### ¿Cómo agrego marcas bidi a la salida de texto?

 Para agregar marcas bidi a la salida de texto, configure el`AddBidiMarks` propiedad de`TxtSaveOptions` a`true`. Por ejemplo:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### ¿Puedo personalizar el carácter de sangría de la lista?

 Sí, puede personalizar el carácter de sangría de la lista configurando el`ListIndentation` propiedad de`TxtSaveOptions`. Por ejemplo, para utilizar un carácter de tabulación para la sangría de la lista, puede hacer lo siguiente:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### ¿Aspose.Words para Java es adecuado para manejar texto multilingüe?

Sí, Aspose.Words para Java es adecuado para manejar texto multilingüe. Admite varios idiomas y codificaciones de caracteres, lo que lo convierte en una opción versátil para trabajar con documentos en diferentes idiomas.

### ¿Cómo puedo acceder a más documentación y recursos para Aspose.Words para Java?

 Puede encontrar documentación y recursos completos para Aspose.Words para Java en el sitio web de documentación de Aspose:[Aspose.Words para la documentación de Java](https://reference.aspose.com/words/java/).

### ¿Dónde puedo descargar Aspose.Words para Java?

 Puede descargar la biblioteca Aspose.Words para Java desde el sitio web de Aspose:[Descargar Aspose.Words para Java](https://releases.aspose.com/words/java/).