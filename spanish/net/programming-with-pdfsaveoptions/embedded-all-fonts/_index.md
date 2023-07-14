---
title: Incrustar fuentes en documento PDF
linktitle: Incrustar fuentes en documento PDF
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para incrustar fuentes en un PDF usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

Este artículo proporciona una guía paso a paso sobre cómo utilizar las fuentes incrustadas en la función de documento PDF de Aspose.Words para .NET. Revisaremos el fragmento de código y explicaremos cada parte en detalle. Al final de este tutorial, podrá comprender cómo incrustar todas las fuentes en un documento y generar un PDF con las fuentes incrustadas utilizando Aspose.Words para .NET.

Antes de comenzar, asegúrese de tener instalada y configurada la biblioteca Aspose.Words para .NET en su proyecto. Puede encontrar la biblioteca y las instrucciones de instalación en el sitio web de Aspose.

## Paso 1: Definir la ruta del directorio del documento

 Para comenzar, debe definir la ruta al directorio donde se encuentran sus documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: Cargue el documento

A continuación, debemos cargar el documento que queremos procesar. En este ejemplo, asumimos que el documento se llama "Rendering.docx" y se encuentra en el directorio de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: Configure las opciones de guardado de PDF

 Para incrustar todas las fuentes en el PDF resultante, necesitamos configurar el`PdfSaveOptions` objeto con el`EmbedFullFonts` propiedad establecida en`true`. Esto garantiza que todas las fuentes utilizadas en el documento se incluyan en el archivo PDF generado.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## Paso 4: Guarde el documento como PDF con fuentes incrustadas

 Finalmente, podemos guardar el documento como un archivo PDF con las fuentes incrustadas. Especifique el nombre del archivo de salida y el`saveOptions` objeto que configuramos en el paso anterior.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

¡Eso es todo! Ha incrustado con éxito todas las fuentes en un documento y ha generado un PDF con las fuentes incrustadas utilizando Aspose.Words para .NET.

### Ejemplo de código fuente para Embedded All Fonts usando Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// El PDF de salida se incrustará con todas las fuentes que se encuentran en el documento.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## Conclusión

En este tutorial, aprendimos cómo incrustar todas las fuentes en un documento PDF usando Aspose.Words para .NET. La incrustación de fuentes garantiza que las fuentes especificadas en el documento estarán disponibles y se mostrarán correctamente, incluso si no están instaladas en el sistema donde se abre el PDF. Esto garantiza una apariencia uniforme y un formato de documento preciso en diferentes dispositivos y plataformas. Siéntase libre de explorar más funciones de Aspose.Words para .NET para optimizar la generación de sus documentos PDF con fuentes incrustadas.

### Preguntas frecuentes

#### P: ¿Qué es incrustar fuentes en un documento PDF y por qué es importante?
R: Incrustar fuentes en un documento PDF es el proceso de incluir todas las fuentes utilizadas en el documento en el propio archivo PDF. Esto garantiza que las fuentes especificadas en el documento estarán disponibles y se mostrarán correctamente, incluso si las fuentes no están instaladas en el sistema donde se abre el PDF. La incrustación de fuentes es importante para preservar la apariencia y el formato del documento, lo que garantiza que las fuentes se reproduzcan de manera uniforme en diferentes dispositivos y plataformas.

#### P: ¿Cómo puedo incrustar todas las fuentes en un documento PDF usando Aspose.Words para .NET?
R: Para incrustar todas las fuentes en un documento PDF usando Aspose.Words para .NET, siga estos pasos:

 Establezca la ruta del directorio del documento reemplazando`"YOUR DOCUMENT DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento que desea procesar utilizando el`Document` clase y la ruta del documento.

 Configure las opciones de guardado de PDF creando una instancia del`PdfSaveOptions` clase y establecer el`EmbedFullFonts` propiedad a`true`. Esto garantiza que todas las fuentes utilizadas en el documento se incrustarán en el archivo PDF generado.

 Guarde el documento en formato PDF con fuentes incrustadas utilizando el`Save` metodo de la`Document`objeto, especificando el nombre del archivo de salida y las opciones de guardado configuradas previamente.

#### P: ¿Por qué es importante incrustar todas las fuentes en un documento PDF?
R: Es importante incrustar todas las fuentes en un documento PDF para garantizar que el documento se muestre correctamente, incluso si las fuentes especificadas no están disponibles en el sistema donde se abre el PDF. Esto ayuda a preservar el aspecto, el formato y la legibilidad del documento, lo que garantiza que las fuentes utilizadas se reproduzcan de manera uniforme en diferentes dispositivos y plataformas.

#### P: ¿Cuáles son los beneficios de incrustar fuentes en un documento PDF?
R: Los beneficios de incrustar fuentes en un documento PDF son:

Garantice una apariencia uniforme del documento: las fuentes incrustadas garantizan que el documento se muestre exactamente como se diseñó, independientemente de las fuentes disponibles en el sistema.

Preservación del formato: las fuentes incrustadas preservan el formato y el diseño del documento, evitando sustituciones de fuentes y variaciones en la apariencia.

Legibilidad mejorada: la incrustación de fuentes garantiza una mejor legibilidad del documento, ya que las fuentes especificadas se utilizan para mostrar el texto, incluso si las fuentes originales no están disponibles.

#### P: ¿Incrustar todas las fuentes aumenta el tamaño del archivo PDF?
R: Sí, incrustar todas las fuentes en un documento PDF puede aumentar el tamaño del archivo PDF generado, ya que los datos de las fuentes deben incluirse en el archivo. Sin embargo, este aumento de tamaño suele ser insignificante para la mayoría de los documentos, y los beneficios de incrustar fuentes a menudo superan este ligero aumento de tamaño.

#### P: ¿Puedo seleccionar fuentes específicas para incrustarlas en un documento PDF?
 R: Sí, con Aspose.Words para .NET puede seleccionar fuentes específicas para incrustarlas en un documento PDF usando opciones de configuración avanzadas. Por ejemplo, puede utilizar el`SubsetFonts`propiedad de la`PdfSaveOptions` objeto para especificar qué fuentes incluir, o usar opciones adicionales para establecer filtros de selección de fuentes personalizados.