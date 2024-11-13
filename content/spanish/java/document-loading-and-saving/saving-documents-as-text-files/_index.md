---
title: Cómo guardar documentos como archivos de texto en Aspose.Words para Java
linktitle: Guardar documentos como archivos de texto
second_title: API de procesamiento de documentos Java Aspose.Words
description: Aprenda a guardar documentos como archivos de texto en Aspose.Words para Java. Siga nuestra guía paso a paso con ejemplos de código Java.
type: docs
weight: 24
url: /es/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Introducción al guardado de documentos como archivos de texto en Aspose.Words para Java

En este tutorial, exploraremos cómo guardar documentos como archivos de texto utilizando la biblioteca Aspose.Words para Java. Aspose.Words es una potente API de Java para trabajar con documentos de Word y ofrece varias opciones para guardar documentos en diferentes formatos, incluido texto sin formato. Cubriremos los pasos para lograrlo y proporcionaremos un código Java de muestra durante el proceso.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Java Development Kit (JDK) instalado en su sistema.
-  Biblioteca Aspose.Words para Java integrada en tu proyecto. Puedes descargarla desde[aquí](https://releases.aspose.com/words/java/).
- Conocimientos básicos de programación Java.

## Paso 1: Crear un documento

Para guardar un documento como archivo de texto, primero debemos crear un documento con Aspose.Words. A continuación, se muestra un fragmento de código Java simple para crear un documento con algún contenido:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

En este código, creamos un nuevo documento y le agregamos texto, incluido texto en diferentes idiomas.

## Paso 2: Definir las opciones para guardar el texto

A continuación, debemos definir las opciones de guardado de texto que especifican cómo se debe guardar el documento como archivo de texto. Podemos configurar varios ajustes, como agregar marcas bidireccionales, sangría de listas y más. Veamos dos ejemplos:

### Ejemplo 1: Adición de marcas bidireccionales

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 En este ejemplo, creamos un`TxtSaveOptions` objeto y establecer el`AddBidiMarks`propiedad a`true` para incluir marcas bidireccionales en la salida de texto.

### Ejemplo 2: Uso del carácter de tabulación para sangrar listas

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Aquí, configuramos las opciones de guardado para utilizar un carácter de tabulación para la sangría de la lista con un conteo de 1.

## Paso 3: Guardar el documento como texto

Ahora que hemos definido las opciones para guardar el texto, podemos guardar el documento como un archivo de texto. El siguiente código demuestra cómo hacerlo:

```java
doc.save("output.txt", saveOptions);
```

 Reemplazar`"output.txt"` con la ruta de archivo deseada donde desea guardar el archivo de texto.

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

En este tutorial, aprendimos a guardar documentos como archivos de texto en Aspose.Words para Java. Cubrimos los pasos para crear un documento, definir opciones de guardado de texto y guardar el documento en formato de texto. Aspose.Words ofrece una gran flexibilidad a la hora de guardar documentos, lo que le permite adaptar el resultado a sus requisitos específicos.

## Preguntas frecuentes

### ¿Cómo agrego marcas bidireccionales a la salida de texto?

 Para agregar marcas bidireccionales a la salida de texto, configure`AddBidiMarks` propiedad de`TxtSaveOptions` a`true`. Por ejemplo:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### ¿Puedo personalizar el carácter de sangría de la lista?

 Sí, puede personalizar el carácter de sangría de la lista configurando el`ListIndentation` propiedad de`TxtSaveOptions`Por ejemplo, para utilizar un carácter de tabulación para sangrar una lista, puede hacer lo siguiente:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### ¿Es Aspose.Words para Java adecuado para gestionar texto multilingüe?

Sí, Aspose.Words para Java es adecuado para manejar texto multilingüe. Admite varios idiomas y codificaciones de caracteres, lo que lo convierte en una opción versátil para trabajar con documentos en diferentes idiomas.

### ¿Cómo puedo acceder a más documentación y recursos para Aspose.Words para Java?

 Puede encontrar documentación y recursos completos para Aspose.Words para Java en el sitio web de documentación de Aspose:[Documentación de Aspose.Words para Java](https://reference.aspose.com/words/java/).

### ¿Dónde puedo descargar Aspose.Words para Java?

 Puede descargar la biblioteca Aspose.Words para Java desde el sitio web de Aspose:[Descargar Aspose.Words para Java](https://releases.aspose.com/words/java/).