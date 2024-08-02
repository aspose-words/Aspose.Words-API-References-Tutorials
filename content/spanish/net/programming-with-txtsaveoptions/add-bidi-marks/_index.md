---
title: Agregar marcas Bidi en un documento de Word
linktitle: Agregar marcas Bidi en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a agregar marcas bidireccionales (Bidi) en documentos de Word usando Aspose.Words para .NET con esta guía. Garantice la dirección adecuada del texto para el contenido en varios idiomas.
type: docs
weight: 10
url: /es/net/programming-with-txtsaveoptions/add-bidi-marks/
---
## Introducción

En el mundo del procesamiento de documentos, el texto bidireccional (Bidi) a menudo puede resultar un poco complicado de gestionar. Esto es especialmente cierto cuando se trata de idiomas que tienen diferentes direcciones de texto, como el árabe o el hebreo. Afortunadamente, Aspose.Words para .NET facilita el manejo de estos escenarios. En este tutorial, veremos cómo agregar marcas Bidi a un documento de Word usando Aspose.Words para .NET.

## Requisitos previos

Antes de profundizar en el código, asegúrese de tener lo siguiente:

1.  Aspose.Words para .NET: Debe tener instalado Aspose.Words para .NET. Puedes descargarlo desde el[Página de descargas de Aspose](https://releases.aspose.com/words/net/).
2. .NET Framework o .NET Core: asegúrese de tener configurado un entorno .NET compatible para ejecutar los ejemplos.
3. Conocimientos básicos de C#: Familiaridad con el lenguaje de programación C# y operaciones básicas en .NET.

## Importar espacios de nombres

Para comenzar, necesita importar los espacios de nombres necesarios. Así es como puedes incluirlos en tu proyecto:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Dividamos el proceso de agregar marcas Bidi en un documento de Word en pasos claros. Cada paso lo guiará a través del código y su propósito.

## Paso 1: configure su documento

 Comience creando una nueva instancia de`Document` clase y un`DocumentBuilder` para agregar contenido al documento.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear el documento y agregar contenido.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 En este paso, inicializa un nuevo documento de Word y configura un`DocumentBuilder` para facilitar la inserción de contenidos.

## Paso 2: agregue contenido a su documento

A continuación, agregue algo de texto a su documento. Aquí agregaremos texto en diferentes idiomas para ilustrar el manejo de texto de Bidi.

```csharp
builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");
```

Aquí, primero agregamos una frase estándar en inglés. Luego, habilitamos el formato de texto Bidi para el texto posterior, que está escrito en hebreo y árabe. Esto demuestra cómo incorporar texto bidireccional.

## Paso 3: configurar las opciones de guardado para las marcas Bidi

 Para garantizar que las marcas Bidi se guarden correctamente en el documento, es necesario configurar el`TxtSaveOptions` y habilitar el`AddBidiMarks` opción.

```csharp
// Agregar marcas Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

 En este paso, creamos una instancia de`TxtSaveOptions` y establecer el`AddBidiMarks`propiedad a`true`. Esto garantiza que las marcas Bidi se incluyan al guardar el documento como un archivo de texto.

## Conclusión

Agregar marcas Bidi a sus documentos de Word puede ser un paso crucial cuando se trata de contenido multilingüe que incluye idiomas con diferentes direcciones de texto. Con Aspose.Words para .NET, este proceso es sencillo y eficiente. Si sigue los pasos descritos anteriormente, puede asegurarse de que sus documentos representen correctamente el texto Bidi, mejorando la legibilidad y la precisión.

## Preguntas frecuentes

### ¿Qué son las marcas Bidi y por qué son importantes?
Las marcas bidi son caracteres especiales que se utilizan para controlar la dirección del texto en los documentos. Son esenciales para mostrar correctamente los idiomas que se leen de derecha a izquierda, como el árabe y el hebreo.

### ¿Puedo usar Aspose.Words para .NET para manejar otros tipos de problemas de dirección de texto?
Sí, Aspose.Words para .NET brinda soporte integral para diversas necesidades de formato y dirección de texto, incluidos los idiomas de derecha a izquierda y de izquierda a derecha.

### ¿Es posible aplicar el formato Bidi únicamente a partes específicas de un documento?
Sí, puede aplicar el formato Bidi a párrafos o secciones específicas de su documento según sea necesario.

### ¿En qué formatos puedo guardar el documento con marcas Bidi?
En el ejemplo proporcionado, el documento se guarda como un archivo de texto. Sin embargo, Aspose.Words también permite guardar documentos en varios formatos conservando las marcas Bidi.

### ¿Dónde puedo encontrar más información sobre Aspose.Words para .NET?
 Puede explorar más sobre Aspose.Words para .NET a través de[Asponer documentación](https://reference.aspose.com/words/net/) y acceder al[Foro de soporte](https://forum.aspose.com/c/words/8) para obtener ayuda adicional.