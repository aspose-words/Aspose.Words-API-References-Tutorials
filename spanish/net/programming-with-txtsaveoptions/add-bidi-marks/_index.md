---
title: Añadir Marcas Bidi
linktitle: Añadir Marcas Bidi
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a agregar marcas Bidi a un documento de Word usando Aspose.Words para .NET y cree documentos multilingües profesionales.
type: docs
weight: 10
url: /es/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Entre las funciones que ofrece Aspose.Words se encuentra la posibilidad de agregar marcas Bidi (bidireccionales) a un documento. En esta guía, lo guiaremos a través de cómo usar el código fuente C# de Aspose.Words para .NET para agregar marcas Bidi a un documento.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una biblioteca popular que hace que trabajar con documentos de Word sea fácil y eficiente. Ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word, incluida la adición de marcas Bidi.

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

En esta guía, hemos explicado cómo usar Aspose.Words para .NET para agregar marcas Bidi a un documento de Word usando el código fuente de C# proporcionado. Siguiendo los pasos provistos, puede agregar fácilmente marcas Bidi a sus documentos de Word en su aplicación C#. Aspose.Words ofrece una gran flexibilidad y potencia para trabajar con formato de texto y gestión de idiomas, lo que le permite crear documentos multilingües de forma profesional.