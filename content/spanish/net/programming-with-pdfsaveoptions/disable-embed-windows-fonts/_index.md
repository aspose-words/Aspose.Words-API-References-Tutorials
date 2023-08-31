---
title: Reduzca el tamaño del PDF deshabilitando las fuentes incrustadas
linktitle: Reduzca el tamaño del PDF deshabilitando las fuentes incrustadas
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a reducir el tamaño de un PDF desactivando la incrustación de fuentes de Windows al convertir documentos a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

En este tutorial, lo guiaremos a través de los pasos para reducir el tamaño de PDF al deshabilitar la incrustación de fuentes de Windows en un documento PDF con Aspose.Words para .NET. Al deshabilitar la incrustación de fuentes, puede reducir el tamaño del archivo PDF generado. Siga los pasos a continuación:

## Paso 1: Cargar el documento

Comience cargando el documento que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento.

## Paso 2: Configure las opciones de guardado de PDF

Cree una instancia de la clase PdfSaveOptions y especifique cómo incrustar fuentes:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Esta opción le permite desactivar la integración de fuentes de Windows en el archivo PDF generado.

## Paso 3: Convertir documento a PDF

 Utilizar el`Save` método para convertir el documento a PDF especificando las opciones de conversión:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Código fuente de ejemplo para deshabilitar fuentes de Windows incrustadas usando Aspose.Words para .NET

Aquí está el código fuente completo para deshabilitar la incrustación de fuentes de Windows en un documento PDF con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// El PDF de salida se guardará sin incrustar las fuentes estándar de Windows.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Siguiendo estos pasos, puede deshabilitar fácilmente la incrustación de fuentes de Windows en un documento PDF con Aspose.Words para .NET.


## Conclusión

En este tutorial, aprendimos cómo reducir el tamaño de un archivo PDF al deshabilitar la incrustación de fuentes de Windows usando Aspose.Words para .NET. Al deshabilitar la incrustación de fuentes, puede reducir el tamaño del archivo PDF generado, lo que facilita el almacenamiento, el intercambio y la transferencia de archivos. Sin embargo, es importante tener en cuenta que deshabilitar la incrustación de fuentes de Windows puede causar cambios en la apariencia y el formato del documento PDF final. Asegúrese de tener en cuenta estas consecuencias al utilizar esta función. Siéntase libre de explorar más funciones de Aspose.Words para .NET para optimizar la generación de sus archivos PDF.

### Preguntas frecuentes

#### P: ¿Qué es deshabilitar la incrustación de fuentes de Windows en un documento PDF y por qué es importante?
R: Deshabilitar la incrustación de fuentes de Windows en un documento PDF es el proceso de evitar que las fuentes de Windows se incluyan en el archivo PDF generado. Esto reduce el tamaño del archivo PDF al eliminar los datos de fuente de Windows incrustados. Esto puede ser importante para reducir el tamaño de los archivos PDF, lo que puede hacer que sea más fácil almacenarlos, compartirlos y transferirlos más rápido.

#### P: ¿Cómo puedo deshabilitar la incrustación de fuentes de Windows en un documento PDF usando Aspose.Words para .NET?
R: Para deshabilitar la incrustación de fuentes de Windows en un documento PDF usando Aspose.Words para .NET, siga estos pasos:

 Cargue el documento que desea convertir a PDF usando el`Document` clase y ruta del documento.

 Crear una instancia de la`PdfSaveOptions`clase y establecer el`FontEmbeddingMode` propiedad a`PdfFontEmbeddingMode.EmbedNone`. Esto deshabilita la incrustación de fuentes de Windows en el archivo PDF generado.

 Utilizar el`Save` metodo de la`Document` objeto para convertir el documento a PDF especificando las opciones de conversión configuradas anteriormente.

#### P: ¿Cuáles son los beneficios de deshabilitar la incrustación de fuentes de Windows en un documento PDF?
R: Los beneficios de deshabilitar la incrustación de fuentes de Windows en un documento PDF son:

Tamaño de archivo PDF reducido: al deshabilitar la incrustación de fuentes de Windows, se eliminan los datos de fuentes de Windows incrustados, lo que reduce el tamaño del archivo PDF generado.

Almacenamiento más fácil: los archivos PDF más pequeños son más fáciles de almacenar, guardar y transferir.

Intercambio y transferencia más rápidos: los archivos PDF más pequeños se pueden compartir y transferir más rápido, ahorrando tiempo y recursos.

#### P: ¿Cuáles son las consecuencias de deshabilitar la incrustación de fuentes de Windows en un documento PDF?
R: Deshabilitar la incrustación de fuentes de Windows en un documento PDF puede tener consecuencias como:

Pérdida de apariencia y formato: si las fuentes de Windows especificadas en el documento no están disponibles en el sistema donde se abre el PDF, se utilizarán fuentes sustitutas, lo que puede dar como resultado una apariencia y un formato incorrectos. forma diferente a la esperada.

Problemas de legibilidad: si las fuentes sustitutas utilizadas no son tan legibles como las fuentes originales, puede afectar la legibilidad del texto en el documento PDF.