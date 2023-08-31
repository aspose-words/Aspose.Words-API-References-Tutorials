---
title: Reduzca el tamaño del documento PDF reduciendo la resolución de las imágenes
linktitle: Reduzca el tamaño del documento PDF reduciendo la resolución de las imágenes
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo reducir el tamaño del documento PDF reduciendo la resolución de las imágenes al convertir a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/downsampling-images/
---

En este tutorial, lo guiaremos a través de los pasos para reducir el tamaño del documento PDF reduciendo la resolución de las imágenes al convertir a PDF con Aspose.Words para .NET. Esto reduce el tamaño del archivo PDF generado. Siga los pasos a continuación:

## Paso 1: cargar el documento

Comience cargando el documento que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento.

## Paso 2: configurar las opciones para guardar PDF

Cree una instancia de la clase PdfSaveOptions y configure las opciones de reducción de escala de la imagen:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 El`Resolution` La propiedad especifica la resolución objetivo de las imágenes y la`ResolutionThreshold`La propiedad especifica la resolución mínima por debajo de la cual las imágenes no se reducirán.

## Paso 3: convertir documento a PDF

 Utilizar el`Save` Método para convertir el documento a PDF especificando opciones de guardado:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Código fuente de ejemplo para reducir la resolución de imágenes usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Podemos establecer un umbral mínimo para la reducción de resolución.
	// Este valor evitará que se reduzca la resolución de la segunda imagen del documento de entrada.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Si sigue estos pasos, puede reducir fácilmente la resolución de la imagen al convertir a PDF con Aspose.Words para .NET.

## Conclusión

En este tutorial, explicamos cómo reducir el tamaño de un documento PDF con muestreo de imágenes al convertirlo a PDF usando Aspose.Words para .NET. Siguiendo los pasos descritos, podrá reducir fácilmente la resolución de las imágenes y el tamaño del archivo PDF generado. Asegúrese de especificar la ruta correcta a su documento y configurar las opciones de muestreo de imágenes según sea necesario. Reducir el tamaño del archivo PDF hace que sea más fácil compartir, almacenar y cargar rápidamente el archivo en diferentes plataformas. Disfrute de los beneficios de reducir el tamaño del documento PDF con muestreo de imágenes utilizando Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Qué significa reducir el tamaño del documento PDF con muestreo de imágenes?
R: Reducir el tamaño del documento PDF con Image Sampling consiste en disminuir el tamaño del archivo PDF generado reduciendo la resolución de las imágenes al convertir a PDF. Esto optimiza el uso del espacio de almacenamiento y facilita compartir y transferir el archivo PDF.

#### P: ¿Cómo puedo reducir el tamaño del documento PDF con muestreo de imágenes usando Aspose.Words para .NET?
R: Para reducir el tamaño del documento PDF con muestreo de imágenes usando Aspose.Words para .NET, siga estos pasos:

 Establezca la ruta del directorio donde se encuentran sus documentos reemplazando`"YOUR DOCUMENTS DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento que desea convertir a PDF usando el`Document` clase y especifique la ruta al documento en el directorio de documentos especificado.

 Configure las opciones de guardar como PDF creando una instancia del`PdfSaveOptions` clase y configurar las opciones de muestreo de imágenes usando el`DownsampleOptions` propiedad. Puede especificar la resolución objetivo de las imágenes utilizando el`Resolution` propiedad y establezca un umbral de resolución mínimo por encima del cual las imágenes no se reducirán utilizando el`ResolutionThreshold` propiedad.

 Guarde el documento en formato PDF utilizando el`Save` método de la`Document`clase que especifica la ruta y las opciones de guardado.

#### P: ¿Cuáles son los beneficios de reducir el tamaño del documento PDF con muestreo de imágenes?
R: Los beneficios de reducir el tamaño del documento PDF con muestreo de imágenes son:

Tamaño de archivo PDF reducido: el muestreo de imágenes reduce la resolución de las imágenes en el documento PDF, lo que resulta en una disminución significativa en el tamaño del archivo PDF. Esto facilita compartir y transferir el archivo, especialmente por correo electrónico o en línea.

Optimización del espacio de almacenamiento: Reducir el tamaño del archivo PDF ayuda a optimizar el uso del espacio de almacenamiento, especialmente cuando tiene muchos archivos PDF que contienen imágenes de alta resolución.

Mejoras de rendimiento: los archivos PDF más pequeños se cargan más rápido y se pueden abrir y ver más rápido en diferentes dispositivos.