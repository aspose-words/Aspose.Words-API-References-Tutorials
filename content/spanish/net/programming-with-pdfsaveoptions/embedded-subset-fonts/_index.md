---
title: Incrustar fuentes de subconjunto en un documento PDF
linktitle: Incrustar fuentes de subconjunto en un documento PDF
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para incrustar subconjuntos de fuentes en un documento PDF usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Este artículo proporciona una guía paso a paso sobre cómo utilizar la función de incrustación de subconjuntos de fuentes con Aspose.Words para .NET. Explicaremos cada parte del código en detalle. Al final de este tutorial, podrá comprender cómo incrustar subconjuntos de fuentes en un documento y generar un PDF que contenga solo los glifos utilizados en el documento.

Antes de comenzar, asegúrese de haber instalado y configurado la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: definir el directorio de documentos

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Sube el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Rendering.docx" y está ubicado en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: Configurar las opciones de guardar como PDF

 Para crear un PDF que contenga solo los subconjuntos de fuentes utilizadas en el documento, debemos configurar el`PdfSaveOptions` objeto con el`EmbedFullFonts` propiedad establecida en`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Paso 4: guarde el documento como PDF con subconjuntos de fuentes

 Finalmente, podemos guardar el documento como PDF usando los subconjuntos de fuentes. Especifique el nombre del archivo de salida y el`saveOptions` objeto que configuramos en el paso anterior.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Eso es todo ! Ha incrustado con éxito subconjuntos de fuentes en un documento y ha generado un PDF que contiene solo los glifos utilizados en el documento con Aspose.Words para .NET.

### Código fuente de muestra para incrustar subconjuntos de fuentes con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// El PDF de salida contendrá subconjuntos de las fuentes del documento.
	// En las fuentes PDF sólo se incluyen los glifos utilizados en el documento.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Conclusión

En este tutorial, aprendimos cómo incrustar subconjuntos de fuentes en un documento PDF usando Aspose.Words para .NET. Incrustar subconjuntos de fuentes ayuda a reducir el tamaño del archivo PDF y al mismo tiempo preserva la apariencia del documento al utilizar solo los caracteres realmente utilizados. Esto garantiza una mejor compatibilidad y rendimiento al ver e imprimir el PDF. No dude en explorar más a fondo las funciones de Aspose.Words para .NET para optimizar la generación de sus documentos PDF con subconjuntos de fuentes incrustados.

### Preguntas frecuentes

#### P: ¿Qué es incrustar subconjuntos de fuentes en un documento PDF?
R: Incrustar subconjuntos de fuentes en un documento PDF es el proceso de incluir solo los glifos utilizados en el documento, en lugar de incluir todas las fuentes completas. Esto reduce el tamaño del archivo PDF al incluir solo los datos de fuente necesarios para mostrar los caracteres realmente utilizados en el documento.

#### P: ¿Cuál es la diferencia entre incrustar fuentes completas e incrustar subconjuntos de fuentes?
R: La incrustación completa de fuentes significa incluir todas las fuentes utilizadas en el documento en el archivo PDF, lo que garantiza que el documento se mostrará exactamente como fue diseñado, pero puede aumentar el tamaño del archivo PDF. Por el contrario, la incrustación de subconjuntos de fuentes contiene solo los glifos utilizados en el documento, lo que reduce el tamaño del archivo PDF, pero limita la capacidad de replicar exactamente el aspecto del documento si se agregan caracteres adicionales más adelante.

#### P: ¿Cómo puedo incrustar subconjuntos de fuentes en un documento PDF usando Aspose.Words para .NET?
R: Para incrustar subconjuntos de fuentes en un documento PDF usando Aspose.Words para .NET, siga estos pasos:

 Establezca la ruta del directorio de documentos reemplazando`"YOUR DOCUMENT DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento que desea procesar utilizando el`Document` clase y la ruta del documento.

 Configure las opciones para guardar PDF creando una instancia del`PdfSaveOptions` clase y establecer el`EmbedFullFonts` propiedad a`false`Esto garantiza que solo los subconjuntos de fuentes utilizados en el documento se incluirán en el archivo PDF.

 Guarde el documento en formato PDF con los subconjuntos de fuentes incrustados usando el`Save` método de la`Document` objeto, especificando el nombre del archivo de salida y las opciones de guardado configuradas anteriormente.

#### P: ¿Cuáles son los beneficios de incrustar subconjuntos de fuentes en un documento PDF?
R: Los beneficios de incrustar subconjuntos de fuentes en un documento PDF son:

Tamaño de archivo PDF reducido: al incluir solo los glifos utilizados en el documento, el tamaño del archivo PDF se reduce en comparación con la incrustación de fuentes completas.

Preservación de la apariencia del documento: Los subconjuntos de fuentes incluidos en el archivo PDF permiten reproducir la apariencia del documento utilizando únicamente los caracteres realmente utilizados.

Compatibilidad con las restricciones de la licencia: es posible que se prefiera incrustar subconjuntos de fuentes en los casos en que las fuentes completas no se puedan incrustar legalmente debido a restricciones de la licencia.