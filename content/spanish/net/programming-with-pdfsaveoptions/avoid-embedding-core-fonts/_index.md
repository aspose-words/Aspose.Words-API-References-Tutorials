---
title: Reduzca el tamaño del archivo PDF al no incrustar fuentes principales
linktitle: Reduzca el tamaño del archivo PDF al no incrustar fuentes principales
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo reducir el tamaño del archivo PDF sin incorporar fuentes principales al convertir documentos de Word a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

En este tutorial, lo guiaremos a través de los pasos para reducir el tamaño del archivo PDF al no incorporar fuentes principales con Aspose.Words para .NET. Esta función le permite controlar si las fuentes básicas como Arial, Times New Roman, etc. deben incrustarse en el PDF al convertir un documento de Word. Siga los pasos a continuación:

## Paso 1: cargar el documento

Comience cargando el documento de Word que desea convertir a PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de especificar la ruta correcta a su documento de Word.

## Paso 2: configurar las opciones de conversión de PDF

Cree una instancia de la clase PdfSaveOptions y habilite la función básica para evitar la incrustación de fuentes:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Esta opción controla si las fuentes base deben incrustarse en el PDF o no.

## Paso 3: convertir documento a PDF

 Utilizar el`Save` Método para convertir el documento de Word a PDF especificando opciones de conversión:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Asegúrese de especificar la ruta correcta para guardar el PDF convertido.

### Código fuente de ejemplo para evitar incrustar fuentes principales usando Aspose.Words para .NET

Aquí está el código fuente completo para usar la función y evitar la incrustación de fuentes principales con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// El PDF de salida no incluirá fuentes principales como Arial, Times New Roman, etc.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Si sigue estos pasos, podrá controlar fácilmente si las fuentes base deben incrustarse en el PDF al convertir un documento de Word con Aspose.Words para .NET.


## Conclusión

En este tutorial, explicamos cómo reducir el tamaño de un archivo PDF al no incorporar fuentes básicas con Aspose.Words para .NET. Esta función le permite controlar si las fuentes base deben incrustarse en el PDF al convertir un documento de Word. Si sigue los pasos descritos, puede controlar fácilmente la incrustación o no incrustación de fuentes básicas, lo que puede ayudar a reducir el tamaño del archivo PDF y garantizar una mejor compatibilidad y una apariencia consistente del documento en diferentes dispositivos y plataformas. No olvide considerar las consecuencias de no incrustar fuentes base y experimentar para asegurarse de que el documento se muestre como se esperaba.

### Preguntas frecuentes

#### P: ¿Cuál es la opción de no incrustar fuentes base en un archivo PDF y por qué es importante?
R: La opción de no incrustar fuentes base en un archivo PDF controla si las fuentes base como Arial, Times New Roman, etc. deben incrustarse en el PDF al convertir un documento de Word. Esto puede ser importante para reducir el tamaño del archivo PDF evitando incluir fuentes comúnmente disponibles en los sistemas de lectura de PDF. También puede ayudar a garantizar una mejor compatibilidad y una apariencia consistente del documento PDF en diferentes dispositivos y plataformas.

#### P: ¿Cómo puedo configurar Aspose.Words para .NET para que no incruste fuentes base en un archivo PDF?
R: Para configurar Aspose.Words para .NET para que no incruste fuentes principales en un archivo PDF, siga estos pasos:

 Establezca la ruta del directorio donde se encuentran sus documentos reemplazando`"YOUR DOCUMENTS DIRECTORY"` con la ruta real de su directorio de documentos.

 Cargue el documento de Word que desea convertir a PDF usando el`Document` clase y la ruta del documento especificada.

 Crear una instancia del`PdfSaveOptions` clase y establecer el`UseCoreFonts`propiedad a`true`. Esto evitará la incrustación de fuentes base en el archivo PDF generado.

 Utilizar el`Save` método de la`Document` objeto para guardar el documento en formato PDF especificando las opciones de conversión configuradas anteriormente.

#### P: ¿Cuáles son los beneficios de no incrustar fuentes base en un archivo PDF?
R: Los beneficios de no incrustar fuentes base en un archivo PDF son:

Reducción del tamaño del archivo PDF: al evitar incrustar fuentes comúnmente disponibles como Arial, Times New Roman, etc., se puede reducir el tamaño del archivo PDF, lo que facilita almacenar, compartir y transferir archivos.

Mejor compatibilidad: al utilizar fuentes básicas comúnmente disponibles en los sistemas lectores de PDF, garantiza una mejor compatibilidad y apariencia del documento en diferentes dispositivos y plataformas.

#### P: ¿Cuáles son las consecuencias de no incrustar fuentes base en un archivo PDF?
R: Las consecuencias de no incrustar fuentes base en un archivo PDF son las siguientes:

Apariencia diferente: si las fuentes base no están disponibles en el sistema donde se abre el PDF, se utilizarán fuentes sustitutas, lo que puede dar como resultado una apariencia diferente a la prevista.

Problemas de legibilidad: las fuentes sustitutas utilizadas pueden no ser tan legibles como las fuentes originales, lo que puede afectar la legibilidad del documento.