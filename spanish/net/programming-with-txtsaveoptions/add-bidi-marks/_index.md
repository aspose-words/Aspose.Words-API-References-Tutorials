---
title: Agregar marcas Bidi en un documento de Word
linktitle: Agregar marcas Bidi en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a agregar marcas Bidi a un documento de Word usando Aspose.Words para .NET y cree documentos multilingües profesionales.
type: docs
weight: 10
url: /es/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Entre las funciones que ofrece Aspose.Words se encuentra la posibilidad de agregar marcas Bidi (bidireccionales) a un documento. En esta guía, lo guiaremos a través de cómo usar el código fuente C# de Aspose.Words para .NET para agregar marcas Bidi a un documento.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una biblioteca popular que hace que el procesamiento de textos con documentos de Word sea fácil y eficiente. Ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word, incluida la adición de marcas Bidi.

## Creación del documento y adición de contenido.

El primer paso es crear un nuevo documento y agregarle contenido. Utilice la clase Document para crear una nueva instancia de documento. Luego use la clase DocumentBuilder para agregar texto al documento. Aquí hay un ejemplo :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

En este ejemplo, creamos un nuevo documento y usamos DocumentBuilder para agregar texto. Hemos agregado tres líneas de texto: una en inglés, una en hebreo y una en árabe para demostrar cómo agregar contenido en diferentes idiomas.

## Marcas Bidi añadidas

Una vez que se ha agregado el contenido, ahora podemos agregar marcas Bidi al documento. Para esto, usamos la clase TxtSaveOptions y establecemos la propiedad AddBidiMarks en true. Así es cómo:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

En este ejemplo, creamos una instancia de TxtSaveOptions y establecemos la propiedad AddBidiMarks en true. A continuación, usamos el método Save de la clase Document para guardar el documento con marcas Bidi.

### Código fuente de ejemplo para la funcionalidad "Agregar marcas Bidi" con Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear el documento y agregar contenido
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Añadir marcas Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Conclusión

En esta guía, hemos explicado cómo usar Aspose.Words para .NET para agregar marcas Bidi a un documento de Word usando el código fuente de C# proporcionado. Siguiendo los pasos provistos, puede agregar fácilmente marcas Bidi a sus documentos de Word en su aplicación C#. Aspose.Words ofrece una gran flexibilidad y potencia para el procesamiento de textos con formato de texto y gestión de idiomas, lo que le permite crear documentos multilingües de forma profesional.

### Preguntas frecuentes

#### P: ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Ofrece muchas funciones para el procesamiento de textos con documentos de Word, incluida la adición de marcas Bidi (bidireccionales).

#### P: ¿Qué funciones ofrece Aspose.Words para .NET?
Aspose.Words para .NET ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word. Algunas de estas características incluyen la creación de documentos, la adición de contenido, el formato de texto, la gestión de tablas, la fusión y división de documentos, la conversión de documentos y más.

#### P: ¿Cómo puedo agregar marcas Bidi a un documento de Word usando Aspose.Words para .NET?
Puede agregar marcas Bidi a un documento de Word siguiendo estos pasos:

 Crear un nuevo documento usando el`Document` clase.

 Utilizar el`DocumentBuilder` class para agregar contenido al documento.

 Una vez que haya agregado el contenido, use el`TxtSaveOptions`clase y establecer el`AddBidiMarks` propiedad a`true`.

 Guarde el documento con marcas Bidi usando el`Save` metodo de la`Document` clase.

#### P: ¿Aspose.Words admite varios idiomas para agregar marcas Bidi?
Sí, Aspose.Words admite varios idiomas para agregar marcas Bidi. Puede agregar marcas Bidi al texto en diferentes idiomas, como inglés, hebreo y árabe, utilizando Aspose.Words para .NET.

#### P: ¿Existen opciones adicionales para guardar el documento con marcas Bidi?
 Sí, puede especificar otras opciones al guardar el documento con marcas Bidi usando el`TxtSaveOptions` clase. Por ejemplo, puede establecer el formato de guardado del documento, las opciones de codificación, etc.