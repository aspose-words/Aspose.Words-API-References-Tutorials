---
title: Reduzca el tamaño del documento PDF con imágenes de reducción de resolución
linktitle: Reduzca el tamaño del documento PDF con imágenes de reducción de resolución
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a reducir el tamaño de un documento PDF reduciendo la resolución de imágenes al convertir a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/downsampling-images/
---

En este tutorial, lo guiaremos a través de los pasos para reducir el tamaño del documento PDF con imágenes de resolución reducida al convertir a PDF con Aspose.Words para .NET. Esto reduce el tamaño del archivo PDF generado. Siga los pasos a continuación:

## Paso 1: Cargar el documento

Comience cargando el documento que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento.

## Paso 2: Configure las opciones de guardado de PDF

Cree una instancia de la clase PdfSaveOptions y establezca las opciones de reducción de escala de la imagen:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 El`Resolution` propiedad especifica la resolución de destino de las imágenes y la`ResolutionThreshold`La propiedad especifica la resolución mínima por debajo de la cual las imágenes no se reducirán.

## Paso 3: Convertir documento a PDF

 Utilizar el`Save` método para convertir el documento a PDF especificando las opciones de guardado:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Código fuente de ejemplo para reducción de resolución de imágenes usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Podemos establecer un umbral mínimo para la reducción de resolución.
	// Este valor evitará que se reduzca la resolución de la segunda imagen en el documento de entrada.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Siguiendo estos pasos, puede reducir fácilmente la resolución de la imagen al convertir a PDF con Aspose.Words para .NET.

## Conclusión

En este tutorial, hemos explicado cómo reducir el tamaño de un documento PDF con muestreo de imágenes al convertirlo a PDF usando Aspose.Words para .NET. Siguiendo los pasos descritos, puede reducir fácilmente la resolución de las imágenes y el tamaño del archivo PDF generado. Asegúrese de especificar la ruta correcta a su documento y configure las opciones de muestreo de imágenes según sea necesario. Reducir el tamaño del archivo PDF facilita compartir, almacenar y cargar rápidamente el archivo en diferentes plataformas. Disfrute de los beneficios de reducir el tamaño del documento PDF con el muestreo de imágenes usando Aspose.Words para .NET.

### Preguntas frecuentes

#### P: ¿Qué es reducir el tamaño del documento PDF con el muestreo de imágenes?
R: Reducir el tamaño del documento PDF con Image Sampling es disminuir el tamaño del archivo PDF generado al reducir la resolución de las imágenes al convertirlas a PDF. Esto optimiza el uso del espacio de almacenamiento y facilita compartir y transferir el archivo PDF.

#### P: ¿Cómo puedo reducir el tamaño del documento PDF con el muestreo de imágenes usando Aspose.Words para .NET?
R: Para reducir el tamaño del documento PDF con muestreo de imágenes usando Aspose.Words para .NET, siga estos pasos:

 Establezca la ruta del directorio donde se encuentran sus documentos reemplazando`"YOUR DOCUMENTS DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento que desea convertir a PDF usando el`Document` class y especifique la ruta al documento en el directorio de documentos especificado.

 Configure las opciones de guardar como PDF creando una instancia del`PdfSaveOptions` clase y configurando las opciones de muestreo de imagen usando el`DownsampleOptions` propiedad. Puede especificar la resolución de destino de las imágenes mediante el`Resolution` propiedad y establezca un umbral de resolución mínimo por encima del cual las imágenes no se reducirán utilizando la`ResolutionThreshold` propiedad.

 Guarde el documento en formato PDF usando el`Save` metodo de la`Document`class especificando la ruta y las opciones de guardado.

#### P: ¿Cuáles son los beneficios de reducir el tamaño del documento PDF con el muestreo de imágenes?
R: Los beneficios de reducir el tamaño del documento PDF con el muestreo de imágenes son:

Tamaño de archivo PDF reducido: el muestreo de imágenes reduce la resolución de las imágenes en el documento PDF, lo que resulta en una disminución significativa del tamaño del archivo PDF. Esto facilita compartir y transferir el archivo, especialmente por correo electrónico o en línea.

Optimización del espacio de almacenamiento: Reducir el tamaño del archivo PDF ayuda a optimizar el uso del espacio de almacenamiento, especialmente cuando tiene muchos archivos PDF que contienen imágenes de alta resolución.

Mejoras de rendimiento: los archivos PDF más pequeños se cargan más rápido y se pueden abrir y ver más rápido en diferentes dispositivos.