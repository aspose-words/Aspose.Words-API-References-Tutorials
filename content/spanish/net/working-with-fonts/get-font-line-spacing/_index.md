---
title: Obtener espacio entre líneas de fuente
linktitle: Obtener espacio entre líneas de fuente
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo obtener el interlineado de fuentes usando Aspose.Words para .NET con este tutorial paso a paso. Perfecto para desarrolladores.
type: docs
weight: 10
url: /es/net/working-with-fonts/get-font-line-spacing/
---
## Introducción

Aspose.Words para .NET es una poderosa biblioteca que le permite crear, manipular y convertir documentos de Word mediante programación. Una tarea común que quizás deba realizar es recuperar el interlineado de una fuente específica en un documento. En este tutorial, lo guiaremos a través del proceso paso a paso, asegurándonos de que pueda obtener fácilmente el interlineado de fuentes usando Aspose.Words para .NET. 

## Requisitos previos

Antes de profundizar en el código, asegúrese de cumplir con los siguientes requisitos previos:

1.  Aspose.Words para la biblioteca .NET: descargue e instale la última versión desde[aquí](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: asegúrese de tener configurado un IDE como Visual Studio.
3. Conocimientos básicos de C#: este tutorial asume que tienes conocimientos básicos de programación en C#.

## Importar espacios de nombres

Primero, necesita importar los espacios de nombres necesarios en su proyecto C#. Estos espacios de nombres le permitirán acceder a las funcionalidades de Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Dividamos el proceso de obtención del interlineado de fuentes en pasos simples y manejables.

## Paso 1: crear un nuevo documento

El primer paso es crear una nueva instancia de documento de Word usando Aspose.Words para .NET.

```csharp
Document doc = new Document();
```

## Paso 2: Inicializar DocumentBuilder

 continuación, necesitamos inicializar el`DocumentBuilder` objeto. Este objeto nos ayudará a construir y manipular el contenido del documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: configurar las propiedades de la fuente

Ahora configuramos las propiedades de fuente para el texto que queremos insertar. Para este ejemplo, usaremos la fuente "Calibri".

```csharp
builder.Font.Name = "Calibri";
```

## Paso 4: escriba texto en el documento

 Usando el`DocumentBuilder` objeto, escriba algo de texto en el documento. Este texto utilizará las propiedades de fuente que configuramos en el paso anterior.

```csharp
builder.Writeln("Sample Text");
```

## Paso 5: recuperar el objeto de fuente

Para obtener el interlineado, debemos acceder al objeto de fuente del texto que acabamos de agregar. Esto se puede hacer navegando a través de la estructura del documento hasta el primer párrafo.

```csharp
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
```

## Paso 6: obtenga el interlineado

Finalmente, recuperamos el interlineado del objeto de fuente y lo imprimimos en la consola.

```csharp
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Conclusión

¡Y ahí lo tienes! Recuperar el interlineado de la fuente usando Aspose.Words para .NET es sencillo si lo divides en estos sencillos pasos. Ya sea que esté creando un documento nuevo o trabajando con uno existente, Aspose.Words proporciona todas las herramientas que necesita para administrar las propiedades de las fuentes de manera eficiente.

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una poderosa biblioteca que permite a los desarrolladores crear, manipular y convertir documentos de Word mediante programación usando C#.

### ¿Puedo usar Aspose.Words para .NET en otros lenguajes .NET?
Sí, puede utilizar Aspose.Words para .NET con cualquier lenguaje .NET, incluidos VB.NET y F#.

### ¿Cómo puedo descargar Aspose.Words para .NET?
 Puede descargar la última versión de Aspose.Words para .NET desde[aquí](https://releases.aspose.com/words/net/).

### ¿Hay una prueba gratuita disponible para Aspose.Words para .NET?
 Sí, puedes obtener una prueba gratuita desde[aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar la documentación de Aspose.Words para .NET?
 La documentación de Aspose.Words para .NET está disponible[aquí](https://reference.aspose.com/words/net/).