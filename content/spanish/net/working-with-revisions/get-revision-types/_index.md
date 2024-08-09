---
title: Obtener tipos de palabras de revisión
linktitle: Obtener tipos de palabras de revisión
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo obtener tipos de palabras de revisión en un documento de Word usando Aspose.Words para .NET. Esta guía paso a paso le ayuda a manejar las revisiones de documentos de manera eficiente.
type: docs
weight: 10
url: /es/net/working-with-revisions/get-revision-types/
---
## Introducción

¿Alguna vez te has encontrado inmerso en un mar de revisiones de documentos, preguntándote quién movió qué y cuándo? No estás solo. Manejar revisiones de documentos puede ser una tarea tediosa, especialmente cuando se trata de documentos extensos. ¡Pero no te preocupes! Con Aspose.Words para .NET, puede identificar y administrar fácilmente estas revisiones. En esta guía, lo guiaremos a través de un proceso paso a paso sobre cómo obtener tipos de palabras de revisión en un documento de Word usando Aspose.Words para .NET. ¡Así que abróchate el cinturón y sumergámonos!

## Requisitos previos

Antes de ensuciarnos las manos con algún código, hay algunas cosas que necesitarás:

1.  Aspose.Words para la biblioteca .NET: si aún no lo ha hecho, descárguelo desde[aquí](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: Visual Studio o cualquier otro IDE compatible con .NET.
3. Conocimientos básicos de C#: será beneficioso comprender el lenguaje de programación C#.
4.  Un documento de Word con revisiones: asegúrese de tener un`.docx`archivo con cambios rastreados para probar el código.

## Importar espacios de nombres

Para comenzar, deberá importar los espacios de nombres necesarios en su proyecto C#. Esto le permitirá acceder a las funcionalidades proporcionadas por Aspose.Words para .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Revision;
using System;
```

Dividamos el ejemplo en varios pasos para una mejor comprensión e implementación.

## Paso 1: configure su directorio de documentos

Lo primero es lo primero, debe definir la ruta a su directorio de documentos. Aquí es donde se ubicará su documento de Word con revisiones.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su carpeta de documentos.

## Paso 2: cargue su documento de Word

A continuación, debe cargar el documento de Word en su proyecto. Este documento debe tener las revisiones que desea analizar.

```csharp
Document doc = new Document(dataDir + "Revisions.docx");
```

 Asegúrese de que el archivo`Revisions.docx` existe en el directorio especificado.

## Paso 3: acceda a la colección de párrafos

Ahora que su documento está cargado, necesita acceder a los párrafos dentro de la primera sección del cuerpo del documento. Esto le ayudará a recorrer cada párrafo para comprobar si hay revisiones.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
```

## Paso 4: iterar a través de los párrafos y verificar si hay revisiones

Aquí es donde ocurre la magia. Repetirá cada párrafo y comprobará si se ha movido (eliminado o insertado).

```csharp
for (int i = 0; i < paragraphs.Count; i++)
{
    if (paragraphs[i].IsMoveFromRevision)
        Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
    if (paragraphs[i].IsMoveToRevision)
        Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

 Este bucle recorre cada párrafo y utiliza el`IsMoveFromRevision`y`IsMoveToRevision` propiedades para determinar si el párrafo se movió (eliminó) o se movió (insertó).

## Conclusión

¡Y ahí lo tienes! Con sólo unas pocas líneas de código, puede identificar fácilmente los tipos de revisiones en su documento de Word utilizando Aspose.Words para .NET. Esta poderosa biblioteca facilita el manejo de revisiones de documentos, permitiéndole concentrarse en tareas más importantes. 

## Preguntas frecuentes

### ¿Puedo utilizar Aspose.Words para .NET para realizar un seguimiento de los cambios realizados por usuarios específicos?

Sí, Aspose.Words para .NET proporciona funcionalidad para acceder a los detalles de la revisión, incluido el autor de los cambios.

### ¿Hay una prueba gratuita disponible para Aspose.Words para .NET?

 ¡Absolutamente! Puedes obtener una prueba gratuita[aquí](https://releases.aspose.com/).

### ¿Cómo puedo solicitar una licencia temporal de Aspose.Words para .NET?

 Puede solicitar y aplicar una licencia temporal desde[aquí](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo encontrar documentación más detallada sobre Aspose.Words para .NET?

 La documentación detallada está disponible en el[Aspose sitio web](https://reference.aspose.com/words/net/).

### ¿Puedo utilizar Aspose.Words para .NET en un proyecto no comercial?

Sí, Aspose.Words para .NET se puede utilizar tanto en proyectos comerciales como no comerciales, pero asegúrese de consultar los términos de la licencia.