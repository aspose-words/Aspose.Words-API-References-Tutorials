---
title: Revisión de forma
linktitle: Revisión de forma
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a manejar revisiones de formas en documentos de Word usando Aspose.Words para .NET con esta guía completa. Domine el seguimiento de cambios, la inserción de formas y más.
type: docs
weight: 10
url: /es/net/working-with-revisions/shape-revision/
---
## Introducción

Editar documentos de Word mediante programación puede ser una tarea desalentadora, especialmente cuando se trata de manejar formas. Ya sea que esté creando informes, diseñando plantillas o simplemente automatizando la creación de documentos, la capacidad de rastrear y administrar revisiones de formas es crucial. Aspose.Words para .NET ofrece una potente API para que este proceso sea fluido y eficiente. En este tutorial, profundizaremos en los detalles de la revisión de formas en documentos de Word, asegurándonos de que tenga las herramientas y el conocimiento para administrar sus documentos con facilidad.

## Requisitos previos

Antes de profundizar en el código, asegurémonos de que tiene todo lo que necesita:

-  Aspose.Words para .NET: asegúrese de tener instalada la biblioteca Aspose.Words. Puede[descárgalo aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: debe tener configurado un entorno de desarrollo, como Visual Studio.
- Comprensión básica de C#: familiaridad con el lenguaje de programación C# y conceptos básicos de programación orientada a objetos.
- Documento de Word: un documento de Word con el que trabajar, o puede crear uno durante el tutorial.

## Importar espacios de nombres

Primero, importemos los espacios de nombres necesarios. Estos nos proporcionarán acceso a las clases y métodos necesarios para manejar documentos y formas de Word.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Paso 1: configurar su directorio de documentos

Antes de comenzar a trabajar con formas, debemos definir la ruta a nuestro directorio de documentos. Aquí es donde guardaremos nuestros documentos modificados.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: crear un nuevo documento

Creemos un nuevo documento de Word donde insertaremos y revisaremos formas.

```csharp
Document doc = new Document();
```

## Paso 3: insertar una forma en línea

Comenzaremos insertando una forma en línea en nuestro documento sin realizar un seguimiento de las revisiones. Una forma en línea es aquella que fluye con el texto.

```csharp
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Paso 4: comenzar a realizar un seguimiento de las revisiones

Para realizar un seguimiento de los cambios en nuestro documento, debemos habilitar el seguimiento de revisiones. Esto es esencial para identificar modificaciones realizadas en las formas.

```csharp
doc.StartTrackRevisions("John Doe");
```

## Paso 5: insertar otra forma con revisiones

Ahora que el seguimiento de revisión está habilitado, insertemos otra forma. Esta vez, se realizará un seguimiento de cualquier cambio.

```csharp
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Paso 6: Recuperar y Modificar Formas

Podemos recuperar todas las formas del documento y modificarlas según sea necesario. Aquí, obtendremos las formas y eliminaremos la primera.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
shapes[0].Remove();
```

## Paso 7: guardar el documento

Después de realizar nuestros cambios, debemos guardar el documento. Esto garantiza que se almacenen todas las revisiones y modificaciones.

```csharp
doc.Save(dataDir + "Revision shape.docx");
```

## Paso 8: Manejo de las revisiones de movimiento de formas

Cuando se mueve una forma, Aspose.Words lo rastrea como una revisión. Esto significa que habrá dos instancias de la forma: una en su ubicación original y otra en su nueva ubicación.

```csharp
doc = new Document(dataDir + "Revision shape.docx");
shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
```

## Conclusión

¡Y ahí lo tienes! Ha aprendido con éxito cómo manejar revisiones de formas en documentos de Word usando Aspose.Words para .NET. Ya sea que esté administrando plantillas de documentos, automatizando informes o simplemente realizando un seguimiento de los cambios, estas habilidades son invaluables. Al seguir esta guía paso a paso, no sólo dominará los conceptos básicos, sino que también obtendrá información sobre técnicas más avanzadas de manejo de documentos.

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una poderosa biblioteca que permite a los desarrolladores crear, modificar y convertir documentos de Word mediante programación usando C#.

### ¿Puedo realizar un seguimiento de los cambios realizados en otros elementos de un documento de Word?
Sí, Aspose.Words para .NET admite el seguimiento de cambios en varios elementos, incluidos texto, tablas y más.

### ¿Cómo puedo obtener una prueba gratuita de Aspose.Words para .NET?
 Puede obtener una prueba gratuita de Aspose.Words para .NET[aquí](https://releases.aspose.com/).

### ¿Es posible aceptar o rechazar revisiones mediante programación?
Sí, Aspose.Words para .NET proporciona métodos para aceptar o rechazar revisiones mediante programación.

### ¿Puedo usar Aspose.Words para .NET con otros lenguajes .NET además de C#?
¡Absolutamente! Aspose.Words para .NET se puede utilizar con cualquier lenguaje .NET, incluidos VB.NET y F#.