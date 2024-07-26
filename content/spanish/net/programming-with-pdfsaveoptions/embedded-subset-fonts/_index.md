---
title: Incrustar fuentes de subconjunto en un documento PDF
linktitle: Incrustar fuentes de subconjunto en un documento PDF
second_title: API de procesamiento de documentos Aspose.Words
description: Reduzca el tamaño del archivo PDF incorporando solo los subconjuntos de fuentes necesarios utilizando Aspose.Words para .NET. Siga nuestra guía paso a paso para optimizar sus archivos PDF de manera eficiente.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---
## Introducción

¿Alguna vez has notado que algunos archivos PDF son mucho más grandes que otros, incluso cuando contienen contenido similar? El culpable suele estar en las fuentes. Incrustar fuentes en un PDF garantiza que se vea igual en cualquier dispositivo, pero también puede aumentar el tamaño del archivo. Afortunadamente, Aspose.Words para .NET ofrece una función útil para incrustar sólo los subconjuntos de fuentes necesarios, manteniendo sus archivos PDF ágiles y eficientes. Este tutorial lo guiará a través del proceso, paso a paso.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

-  Aspose.Words para .NET: puedes descargarlo[aquí](https://releases.aspose.com/words/net/).
- Entorno .NET: asegúrese de tener un entorno de desarrollo .NET que funcione.
- Conocimientos básicos de C#: la familiaridad con la programación en C# le ayudará a seguir adelante.

## Importar espacios de nombres

Para utilizar Aspose.Words para .NET, debe importar los espacios de nombres necesarios en su proyecto. Agregue estos en la parte superior de su archivo C#:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Paso 1: cargue el documento

 Primero, necesitamos cargar el documento de Word que queremos convertir a PDF. Esto se hace usando el`Document` clase proporcionada por Aspose.Words.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Este fragmento de código carga el documento ubicado en`dataDir` . Asegúrate de reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su documento.

## Paso 2: configurar las opciones de guardar PDF

 A continuación configuramos el`PdfSaveOptions` para garantizar que solo se incrusten los subconjuntos de fuentes necesarios. Configurando`EmbedFullFonts` a`false`, le decimos a Aspose.Words que incruste solo los glifos utilizados en el documento.

```csharp
// El PDF de salida contendrá subconjuntos de las fuentes del documento.
// En las fuentes PDF sólo se incluyen los glifos utilizados en el documento.
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

Este pequeño pero crucial paso ayuda a reducir significativamente el tamaño del archivo PDF.

## Paso 3: guarde el documento como PDF

 Finalmente guardamos el documento como PDF usando el`Save` método, aplicando el configurado`PdfSaveOptions`.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf", saveOptions);
```

 Este código generará un archivo PDF con el nombre`WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf` en el directorio especificado, con solo los subconjuntos de fuentes necesarios incrustados.

## Conclusión

¡Y ahí lo tienes! Si sigue estos sencillos pasos, puede reducir de manera eficiente el tamaño de sus archivos PDF incorporando solo los subconjuntos de fuentes necesarios usando Aspose.Words para .NET. Esto no sólo ahorra espacio de almacenamiento sino que también garantiza tiempos de carga más rápidos y un mejor rendimiento, especialmente para documentos con muchas fuentes.

## Preguntas frecuentes

### ¿Por qué debería incrustar sólo subconjuntos de fuentes en un PDF?
Incrustar sólo los subconjuntos de fuentes necesarios puede reducir significativamente el tamaño del archivo PDF sin comprometer la apariencia y legibilidad del documento.

### ¿Puedo volver a incrustar fuentes completas si es necesario?
 Sí tu puedes. Simplemente configure el`EmbedFullFonts`propiedad a`true` en el`PdfSaveOptions`.

### ¿Aspose.Words para .NET admite otras funciones de optimización de PDF?
¡Absolutamente! Aspose.Words para .NET ofrece una variedad de opciones para optimizar archivos PDF, incluida la compresión de imágenes y la eliminación de objetos no utilizados.

### ¿Qué tipos de fuentes se pueden incrustar en subconjuntos utilizando Aspose.Words para .NET?
Aspose.Words para .NET admite la incrustación de subconjuntos para todas las fuentes TrueType utilizadas en el documento.

### ¿Cómo puedo verificar qué fuentes están incrustadas en mi PDF?
Puede abrir el PDF en Adobe Acrobat Reader y verificar las propiedades en la pestaña Fuentes para ver las fuentes incrustadas.
