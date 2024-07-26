---
title: Optimice el tamaño del PDF con omitir fuentes Arial y Times Roman incrustadas
linktitle: Optimice el tamaño del PDF con omitir fuentes Arial y Times Roman incrustadas
second_title: API de procesamiento de documentos Aspose.Words
description: Optimice el tamaño del PDF omitiendo las fuentes Arial y Times Roman incrustadas usando Aspose.Words para .NET. Siga esta guía paso a paso para optimizar sus archivos PDF.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---
## Introducción

¿Alguna vez te has encontrado en una situación en la que el tamaño de tu archivo PDF es demasiado grande? Es como hacer las maletas para unas vacaciones y darse cuenta de que la maleta está a punto de estallar. Sabes que necesitas perder algo de peso, pero ¿qué dejas ir? Al trabajar con archivos PDF, especialmente aquellos convertidos a partir de documentos de Word, las fuentes incrustadas pueden aumentar el tamaño del archivo. Afortunadamente, Aspose.Words para .NET proporciona una solución elegante para mantener sus archivos PDF ágiles y sencillos. En este tutorial, veremos cómo optimizar el tamaño de su PDF omitiendo las fuentes incrustadas Arial y Times Roman. ¡Empecemos!

## Requisitos previos

Antes de entrar en el meollo de la cuestión, hay algunas cosas que necesitará:
-  Aspose.Words para .NET: asegúrese de tener instalada esta potente biblioteca. Si no, puedes descargarlo desde[aquí](https://releases.aspose.com/words/net/).
- Un conocimiento básico de C#: esto le ayudará a seguir los fragmentos de código.
- Un documento de Word: usaremos un documento de muestra para demostrar el proceso. 

## Importar espacios de nombres

Lo primero es lo primero, asegúrese de haber importado los espacios de nombres necesarios. Esto prepara el escenario para acceder a las funcionalidades de Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Muy bien, analicemos el proceso paso a paso.

## Paso 1: configure su entorno

Para comenzar, necesita configurar su entorno de desarrollo. Abra su IDE de C# favorito (como Visual Studio) y cree un nuevo proyecto.

## Paso 2: cargue el documento de Word

El siguiente paso es cargar el documento de Word que desea convertir a PDF. Asegúrese de que su documento esté en el directorio correcto.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 En este fragmento, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta a su directorio de documentos.

## Paso 3: configurar las opciones de guardar PDF

Ahora, necesitamos configurar las opciones de guardar PDF para controlar cómo se incrustan las fuentes. De forma predeterminada, todas las fuentes están incrustadas, lo que puede aumentar el tamaño del archivo. Cambiaremos esta configuración.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll
};
```

## Paso 4: guarde el documento como PDF

Finalmente, guarde el documento como PDF con las opciones de guardado especificadas. Aquí es donde ocurre la magia.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Este comando guarda su documento como un PDF llamado "OptimizedPDF.pdf" en el directorio especificado.

## Conclusión

¡Y ahí lo tienes! Acaba de aprender cómo optimizar el tamaño de su archivo PDF omitiendo la incrustación de fuentes Arial y Times Roman usando Aspose.Words para .NET. Este simple ajuste puede reducir significativamente el tamaño de sus archivos, haciéndolos más fáciles de compartir y almacenar. Es como ir al gimnasio a buscar archivos PDF, perder peso innecesario y mantener intactos todos los elementos esenciales.

## Preguntas frecuentes

### ¿Por qué debería omitir la incorporación de fuentes Arial y Times Roman?
Omitir estas fuentes comunes puede reducir el tamaño de su archivo PDF, ya que la mayoría de los sistemas ya tienen estas fuentes instaladas.

### ¿Esto afectará la apariencia de mi PDF?
No, no lo será. Dado que Arial y Times Roman son fuentes estándar, la apariencia sigue siendo constante en los diferentes sistemas.

### ¿Puedo omitir la inserción de otras fuentes también?
Sí, puede configurar las opciones de guardar para omitir la incorporación de otras fuentes si es necesario.

### ¿Aspose.Words para .NET es gratuito?
Aspose.Words para .NET ofrece una prueba gratuita que puedes descargar[aquí](https://releases.aspose.com/) , pero para tener acceso completo, necesitas comprar una licencia[aquí](https://purchase.aspose.com/buy).

### ¿Dónde puedo encontrar más tutoriales sobre Aspose.Words para .NET?
 Puede encontrar documentación completa y tutoriales.[aquí](https://reference.aspose.com/words/net/).