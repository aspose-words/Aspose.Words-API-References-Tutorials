---
title: Código vallado
linktitle: Código vallado
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a agregar código delimitado y cadenas de información a documentos de Word utilizando Aspose.Words para .NET. Guía paso a paso incluida. Mejore sus habilidades de formato de documentos.
type: docs
weight: 10
url: /es/net/working-with-markdown/fenced-code/
---
## Introducción

¡Hola, compañero codificador! Hoy, nos sumergimos en el mundo de Aspose.Words para .NET para dominar el arte de agregar código delimitado y código delimitado con cadenas de información a sus documentos de Word. Imagine su documento de Word como un lienzo y usted, el artista, está a punto de pintar con la precisión de un desarrollador experimentado. Con Aspose.Words, obtiene el poder de mejorar sus documentos mediante programación con bloques de código estructurados y formateados, haciendo que sus documentos técnicos brillen con profesionalismo y claridad.

## Requisitos previos

Antes de pasar al tutorial, asegurémonos de que tiene todo lo que necesita:

- Conocimientos básicos de C#: una comprensión general de C# le ayudará a comprender los conceptos rápidamente.
-  Aspose.Words para .NET: Debe tener instalado Aspose.Words para .NET. Si aún no lo tienes, cógelo.[aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: Visual Studio o cualquier otro IDE de C# con el que se sienta cómodo.

## Importar espacios de nombres

Lo primero es lo primero: debe importar los espacios de nombres necesarios. Esto es como reunir todas tus herramientas antes de comenzar un proyecto.

```csharp
using Aspose.Words;
using Aspose.Words.Style;
```

Ahora, analicemos el proceso paso a paso.

## Paso 1: configurar su proyecto

Antes de que podamos crear hermosos bloques de código formateados en nuestro documento de Word, debemos configurar un nuevo proyecto en Visual Studio.

1. Cree un nuevo proyecto: abra Visual Studio y cree una nueva aplicación de consola C#.
2. Agregue la referencia de Aspose.Words: instale Aspose.Words a través del Administrador de paquetes NuGet. Puede hacer esto haciendo clic derecho en su proyecto en el Explorador de soluciones, seleccionando "Administrar paquetes NuGet" y buscando Aspose.Words.

## Paso 2: Inicialice DocumentBuilder

Ahora que su proyecto está configurado, inicialicemos DocumentBuilder, que será nuestra herramienta principal para agregar contenido al documento de Word.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Paso 3: crea un estilo para código delimitado

Para agregar código delimitado, primero debemos crear un estilo. Piense en esto como establecer el tema para nuestro bloque de código.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
fencedCode.Font.Name = "Courier New";
fencedCode.Font.Size = 10;
fencedCode.ParagraphFormat.LeftIndent = 20;
fencedCode.ParagraphFormat.RightIndent = 20;
fencedCode.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Paso 4: agregue código protegido al documento

Con nuestro estilo listo, ahora podemos agregar un bloque de código delimitado al documento.

```csharp
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is a fenced code block");
```

## Paso 5: cree un estilo para código protegido con cadena de información

A veces, es posible que desees especificar el lenguaje de programación o agregar información adicional a tu bloque de código. Creemos un estilo para eso.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
fencedCodeWithInfo.Font.Name = "Courier New";
fencedCodeWithInfo.Font.Size = 10;
fencedCodeWithInfo.ParagraphFormat.LeftIndent = 20;
fencedCodeWithInfo.ParagraphFormat.RightIndent = 20;
fencedCodeWithInfo.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Paso 6: agregue código protegido con cadena de información al documento

Ahora, agreguemos un bloque de código delimitado con una cadena de información para indicar que es código C#.

```csharp
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code block with info string - C#");
```

## Conclusión

¡Felicidades! Acaba de agregar bloques de código delimitado y código delimitado con cadenas de información a sus documentos de Word utilizando Aspose.Words para .NET. Esto es sólo la punta del iceberg. Con Aspose.Words, puede automatizar y mejorar el procesamiento de documentos a nuevos niveles. ¡Sigue explorando y codificando felizmente!

## Preguntas frecuentes

### ¿Qué es Aspose.Words para .NET?
Aspose.Words para .NET es una poderosa biblioteca que permite a los desarrolladores crear, manipular y convertir documentos de Word mediante programación.

### ¿Puedo utilizar Aspose.Words con otros lenguajes de programación?
Aspose.Words admite principalmente lenguajes .NET, pero hay versiones disponibles para Java, Python y otros lenguajes.

### ¿Aspose.Words es de uso gratuito?
 Aspose.Words es un producto comercial, pero puedes descargar una prueba gratuita[aquí](https://releases.aspose.com/)para explorar sus características.

### ¿Cómo puedo obtener soporte para Aspose.Words?
 Puede obtener soporte de la comunidad y los desarrolladores de Aspose.[aquí](https://forum.aspose.com/c/words/8).

### ¿Qué otras características ofrece Aspose.Words?
Aspose.Words ofrece una amplia gama de funciones que incluyen conversión de documentos, generación de documentos basada en plantillas, informes y mucho más.