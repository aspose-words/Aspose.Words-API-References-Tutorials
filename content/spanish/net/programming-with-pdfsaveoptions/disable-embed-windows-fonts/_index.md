---
title: Reduzca el tamaño del PDF deshabilitando las fuentes incrustadas
linktitle: Reduzca el tamaño del PDF deshabilitando las fuentes incrustadas
second_title: API de procesamiento de documentos Aspose.Words
description: Reduzca el tamaño del PDF deshabilitando las fuentes incrustadas usando Aspose.Words para .NET. Siga nuestra guía paso a paso para optimizar sus documentos para almacenarlos y compartirlos de manera eficiente.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---
## Introducción

Reducir el tamaño de los archivos PDF puede ser crucial para un almacenamiento eficiente y un intercambio rápido. Una forma eficaz de hacerlo es desactivando las fuentes incrustadas, especialmente cuando las fuentes estándar ya están disponibles en la mayoría de los sistemas. En este tutorial, exploraremos cómo reducir el tamaño de un PDF deshabilitando las fuentes incrustadas usando Aspose.Words para .NET. Revisaremos cada paso para asegurarnos de que pueda implementarlo fácilmente en sus propios proyectos.

## Requisitos previos

Antes de profundizar en el código, asegúrese de tener lo siguiente:

-  Aspose.Words para .NET: si aún no lo ha hecho, descárguelo e instálelo desde[Enlace de descarga](https://releases.aspose.com/words/net/).
- Un entorno de desarrollo .NET: Visual Studio es una opción popular.
- Un documento de Word de muestra: tenga listo un archivo DOCX que desee convertir a PDF.

## Importar espacios de nombres

Para comenzar, asegúrese de haber importado los espacios de nombres necesarios a su proyecto. Esto le permite acceder a las clases y métodos necesarios para nuestra tarea.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Dividamos el proceso en pasos simples y manejables. Cada paso lo guiará a través de la tarea, asegurándose de que comprenda lo que sucede en cada punto.

## Paso 1: Inicialice su documento

Primero, necesitamos cargar el documento de Word que desea convertir a PDF. Aquí es donde comienza tu viaje.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Aquí,`dataDir` es un marcador de posición para el directorio donde se encuentra su documento. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con el camino real.

## Paso 2: configurar las opciones de guardar PDF

A continuación, configuraremos las opciones para guardar PDF. Aquí es donde especificamos que no queremos incrustar las fuentes estándar de Windows.

```csharp
// El PDF de salida se guardará sin incrustar fuentes estándar de Windows.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone
};
```

 Configurando`FontEmbeddingMode` a`EmbedNone`, le indicamos a Aspose.Words que no incluya estas fuentes en el PDF, lo que reduce el tamaño del archivo.

## Paso 3: guarde el documento como PDF

Finalmente guardamos el documento como PDF usando las opciones de guardado configuradas. Este es el momento de la verdad en el que tu DOCX se transforma en un PDF compacto.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta de su directorio real una vez más. El PDF de salida ahora se guardará en el directorio especificado sin fuentes estándar integradas.

## Conclusión

Si sigue estos pasos, podrá reducir significativamente el tamaño de sus archivos PDF. Deshabilitar las fuentes incrustadas es una forma sencilla pero efectiva de hacer que sus documentos sean más livianos y fáciles de compartir. Aspose.Words para .NET hace que este proceso sea fluido, garantizando que pueda optimizar sus archivos con el mínimo esfuerzo.

## Preguntas frecuentes

### ¿Por qué debería desactivar las fuentes incrustadas en un PDF?
Deshabilitar las fuentes incrustadas puede reducir significativamente el tamaño del archivo de un PDF, haciéndolo más eficiente para el almacenamiento y más rápido para compartir.

### ¿El PDF seguirá mostrándose correctamente sin fuentes incrustadas?
Sí, siempre que las fuentes sean estándar y estén disponibles en el sistema donde se visualiza el PDF, se mostrará correctamente.

### ¿Puedo incrustar selectivamente sólo ciertas fuentes en un PDF?
Sí, Aspose.Words para .NET le permite personalizar qué fuentes están incrustadas, lo que brinda flexibilidad a la hora de reducir el tamaño del archivo.

### ¿Necesito Aspose.Words para .NET para desactivar las fuentes incrustadas en archivos PDF?
Sí, Aspose.Words para .NET proporciona la funcionalidad necesaria para configurar opciones de incrustación de fuentes en archivos PDF.

### ¿Cómo obtengo soporte si tengo problemas?
 Puedes visitar el[Foro de soporte](https://forum.aspose.com/c/words/8) para obtener ayuda con cualquier problema que encuentre.
