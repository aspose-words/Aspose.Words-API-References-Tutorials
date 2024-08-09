---
title: Formato 1Bpp Indexado
linktitle: Formato 1Bpp Indexado
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo convertir un documento de Word en una imagen indexada de 1 Bpp usando Aspose.Words para .NET. Siga nuestra guía paso a paso para una fácil conversión.
type: docs
weight: 10
url: /es/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
## Introducción

¿Alguna vez te has preguntado cómo guardar un documento de Word como una imagen en blanco y negro con sólo unas pocas líneas de código? ¡Pues estás de suerte! Hoy, nos sumergimos en un pequeño truco usando Aspose.Words para .NET que le permite convertir sus documentos en imágenes indexadas de 1 Bpp. Este formato es perfecto para ciertos tipos de archivo digital, impresión o cuando necesitas ahorrar espacio. Desglosaremos cada paso para que sea muy fácil. ¿Listo para empezar? ¡Vamos a sumergirnos!

## Requisitos previos

Antes de ensuciarnos las manos, hay algunas cosas que debes tener en cuenta:

-  Aspose.Words para .NET: asegúrese de tener la biblioteca instalada. Puede[descárgalo aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo .NET: Visual Studio es una buena opción, pero puedes utilizar cualquier entorno con el que te sientas cómodo.
- Conocimientos básicos de C#: no se preocupe, lo haremos sencillo, pero un poco de familiaridad con C# le ayudará.
- Un documento de Word: tenga un documento de Word de muestra listo para convertir.

## Importar espacios de nombres

Lo primero es lo primero, necesitamos importar los espacios de nombres necesarios. Esto es crucial ya que nos permite acceder a las clases y métodos que necesitamos desde Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Paso 1: configure su directorio de documentos

Deberá especificar la ruta a su directorio de documentos. Aquí es donde se almacena su documento de Word y donde se guardará la imagen convertida.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue el documento de Word

 Ahora, carguemos el documento de Word en Aspose.Words.`Document` objeto. Este objeto representa su archivo de Word y le permite manipularlo.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: configurar las opciones para guardar imágenes

 A continuación, debemos configurar el`ImageSaveOptions`Aquí es donde ocurre la magia. Lo configuraremos para guardar la imagen en formato PNG con modo de color indexado de 1 Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1),
    ImageColorMode = ImageColorMode.BlackAndWhite,
    PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

- SaveFormat.Png: Esto especifica que queremos guardar el documento como una imagen PNG.
- PageSet(1): Esto indica que solo estamos convirtiendo la primera página.
- ImageColorMode.BlackAndWhite: establece la imagen en blanco y negro.
- ImagePixelFormat.Format1bppIndexed: esto establece el formato de imagen en 1 Bpp indexado.

## Paso 4: guarde el documento como imagen

 Finalmente guardamos el documento como imagen usando el`Save` método de la`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

## Conclusión

¡Y ahí lo tienes! Con solo unas pocas líneas de código, ha transformado su documento de Word en una imagen indexada de 1 Bpp usando Aspose.Words para .NET. Este método es increíblemente útil para crear imágenes de alto contraste y que ahorren espacio a partir de sus documentos. Ahora puede integrar esto fácilmente en sus proyectos y flujos de trabajo. ¡Feliz codificación!

## Preguntas frecuentes

### ¿Qué es una imagen indexada de 1 Bpp?
Una imagen indexada de 1 Bpp (1 bit por píxel) es un formato de imagen en blanco y negro en el que cada píxel está representado por un único bit, ya sea 0 o 1. Este formato ocupa muy poco espacio.

### ¿Puedo convertir varias páginas de un documento de Word a la vez?
 Sí, puedes. Modificar el`PageSet` propiedad en el`ImageSaveOptions` para incluir varias páginas o el documento completo.

### ¿Necesito una licencia para usar Aspose.Words para .NET?
 Sí, Aspose.Words para .NET requiere una licencia para su funcionalidad completa. Puedes conseguir un[licencia temporal aquí](https://purchase.aspose.com/temporary-license/).

### ¿A qué otros formatos de imagen puedo convertir mi documento de Word?
 Aspose.Words admite varios formatos de imagen, incluidos JPEG, BMP y TIFF. Simplemente cambia el`SaveFormat` en el`ImageSaveOptions`.

### ¿Dónde puedo encontrar más documentación sobre Aspose.Words para .NET?
 Puede encontrar documentación detallada en el[Página de documentación de Aspose.Words para .NET](https://reference.aspose.com/words/net/).
