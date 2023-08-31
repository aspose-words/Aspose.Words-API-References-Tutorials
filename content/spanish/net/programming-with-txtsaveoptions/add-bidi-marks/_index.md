---
title: Agregar marcas Bidi en un documento de Word
linktitle: Agregar marcas Bidi en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a agregar marcas Bidi a un documento de Word usando Aspose.Words para .NET y cree documentos multilingües profesionales.
type: docs
weight: 10
url: /es/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Entre las características que ofrece Aspose.Words está la capacidad de agregar marcas Bidi (bidireccionales) a un documento. En esta guía, le explicaremos cómo utilizar el código fuente C# de Aspose.Words para .NET para agregar marcas Bidi a un documento.

## Comprender la biblioteca Aspose.Words

Antes de profundizar en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una biblioteca popular que hace que el procesamiento de palabras con documentos de Word sea fácil y eficiente. Ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word, incluida la adición de marcas Bidi.

## Crear el documento y agregar contenido.

El primer paso es crear un nuevo documento y agregarle contenido. Utilice la clase Documento para crear una nueva instancia de documento. Luego use la clase DocumentBuilder para agregar texto al documento. Aquí hay un ejemplo :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

En este ejemplo, creamos un nuevo documento y usamos DocumentBuilder para agregar texto. Agregamos tres líneas de texto: una en inglés, una en hebreo y otra en árabe para demostrar cómo agregar contenido en diferentes idiomas.

## Se agregaron marcas Bidi

Una vez agregado el contenido, ahora podemos agregar marcas Bidi al documento. Para esto usamos la clase TxtSaveOptions y configuramos la propiedad AddBidiMarks en verdadero. Así es cómo:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

En este ejemplo, creamos una instancia de TxtSaveOptions y configuramos la propiedad AddBidiMarks en verdadero. A continuación, utilizamos el método Guardar de la clase Documento para guardar el documento con marcas Bidi.

### Código fuente de ejemplo para la funcionalidad "Agregar marcas Bidi" con Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear el documento y agregar contenido.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Agregar marcas Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Conclusión

En esta guía, explicamos cómo usar Aspose.Words para .NET para agregar marcas Bidi a un documento de Word utilizando el código fuente C# proporcionado. Siguiendo los pasos proporcionados, puede agregar fácilmente marcas Bidi a sus documentos de Word en su aplicación C#. Aspose.Words ofrece una tremenda flexibilidad y potencia para el procesamiento de textos con formato de texto y gestión de idiomas, lo que le permite crear documentos multilingües de forma profesional.

### Preguntas frecuentes

#### P: ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Ofrece muchas funciones para el procesamiento de textos con documentos de Word, incluida la adición de marcas Bidi (bidireccionales).

#### P: ¿Qué características ofrece Aspose.Words para .NET?
Aspose.Words para .NET ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word. Algunas de estas funciones incluyen la creación de documentos, agregar contenido, formatear texto, administrar tablas, fusionar y dividir documentos, convertir documentos y más.

#### P: ¿Cómo puedo agregar marcas Bidi a un documento de Word usando Aspose.Words para .NET?
Puede agregar marcas Bidi a un documento de Word siguiendo estos pasos:

 Cree un nuevo documento utilizando el`Document` clase.

 Utilizar el`DocumentBuilder` clase para agregar contenido al documento.

 Una vez que haya agregado el contenido, use el`TxtSaveOptions`clase y establecer el`AddBidiMarks` propiedad a`true`.

 Guarde el documento con marcas Bidi usando el`Save` método de la`Document` clase.

#### P: ¿Aspose.Words admite varios idiomas para agregar marcas Bidi?
Sí, Aspose.Words admite varios idiomas para agregar marcas Bidi. Puede agregar marcas Bidi al texto en diferentes idiomas, como inglés, hebreo y árabe, utilizando Aspose.Words para .NET.

#### P: ¿Existen opciones adicionales para guardar el documento con marcas Bidi?
 Sí, puede especificar otras opciones al guardar el documento con marcas Bidi usando el`TxtSaveOptions` clase. Por ejemplo, puede configurar el formato para guardar el documento, las opciones de codificación, etc.