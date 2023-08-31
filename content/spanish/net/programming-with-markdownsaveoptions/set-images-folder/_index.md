---
title: Establecer carpeta de imágenes
linktitle: Establecer carpeta de imágenes
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo configurar la carpeta de imágenes al exportar a Markdown con Aspose.Words para .NET. Personalice la ubicación de las imágenes para una mejor organización e integración.
type: docs
weight: 10
url: /es/net/programming-with-markdownsaveoptions/set-images-folder/
---

Aquí hay una guía paso a paso para explicar el siguiente código fuente de C# que ayuda a configurar la carpeta de imágenes para las opciones de exportación de Markdown usando la biblioteca Aspose.Words para .NET. Asegúrese de haber incluido la biblioteca Aspose.Words en su proyecto antes de usar este código.

## Paso 1: establecer la ruta del directorio de documentos

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Asegúrese de especificar la ruta correcta al directorio de documentos donde se encuentra el documento que contiene las imágenes.

## Paso 2: Cargue el documento que contiene las imágenes.

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Cargamos el documento especificado que contiene las imágenes que queremos exportar con opciones de Markdown.

## Paso 3: configure la carpeta de imágenes para las opciones de exportación de Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Creamos una instancia de`MarkdownSaveOptions` y establezca la ruta a la carpeta de imágenes usando el`ImagesFolder` propiedad. Asegúrese de especificar la ruta correcta a la carpeta donde desea guardar las imágenes exportadas.

## Paso 4: guarde el documento con las opciones de exportación de Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Guardamos el documento en un flujo de memoria usando las opciones de exportación de Markdown especificadas. Luego puede usar el flujo para realizar otras operaciones, como guardar contenido de Markdown en un archivo.

### Código fuente de ejemplo para configurar la carpeta de imágenes para MarkdownSaveOptions con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Este código fuente demuestra cómo cargar un documento que contiene imágenes y luego configurar la carpeta de imágenes para las opciones de exportación de Markdown. Usando las opciones especificadas, el documento se guarda en una secuencia de memoria. Esto le permite personalizar la ubicación de la carpeta de imágenes al exportar contenido de Markdown.