---
title: Reduzca el tamaño del PDF escalando fuentes Wmf al tamaño de metarchivo
linktitle: Reduzca el tamaño del PDF escalando fuentes Wmf al tamaño de metarchivo
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para reducir el tamaño de un PDF escalando fuentes WMF al tamaño de un metarchivo al convertir a PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---
## Introducción

Cuando se trabaja con archivos PDF, especialmente aquellos generados a partir de documentos de Word que contienen gráficos WMF (Metarchivo de Windows), la gestión del tamaño puede convertirse en un aspecto crucial del manejo de documentos. Una forma de controlar el tamaño del PDF es ajustando cómo se representan las fuentes WMF dentro del documento. En este tutorial, exploraremos cómo reducir el tamaño de un PDF escalando las fuentes WMF al tamaño del metarchivo usando Aspose.Words para .NET.

## Requisitos previos

Antes de profundizar en los pasos, asegúrese de tener lo siguiente:

1. Aspose.Words para .NET: asegúrese de tener instalada la biblioteca Aspose.Words. Si no, puedes[descarguelo aqui](https://releases.aspose.com/words/net/).
2. Entorno de desarrollo: este tutorial asume que tiene configurado un entorno de desarrollo .NET (como Visual Studio) donde puede escribir y ejecutar código C#.
3. Comprensión básica de la programación .NET: será útil estar familiarizado con los conceptos básicos de programación .NET y la sintaxis de C#.
4. Documento de Word con gráficos WMF: necesitará un documento de Word que contenga gráficos WMF. Puede utilizar su propio documento o crear uno para realizar pruebas.

## Importar espacios de nombres

Primero, necesita importar los espacios de nombres necesarios en su proyecto C#. Esto le dará acceso a las clases y métodos necesarios para trabajar con Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Paso 1: cargue el documento de Word

 Para comenzar, cargue el documento de Word que contiene los gráficos WMF. Esto se hace usando el`Document` clase de Aspose.Words.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Cargar el documento
Document doc = new Document(dataDir + "WMF with text.docx");
```

 Aquí,`dataDir` es un marcador de posición para la ruta del directorio de documentos. Creamos una instancia del`Document` clase pasando la ruta al archivo de Word. Esto carga el documento en la memoria, listo para su posterior procesamiento.

## Paso 2: configurar las opciones de representación de metarchivos

 A continuación, debe configurar las opciones de representación del metarchivo. Específicamente, establezca el`ScaleWmfFontsToMetafileSize`propiedad a`false`. Esto controla si las fuentes WMF se escalan para que coincidan con el tamaño del metarchivo.

```csharp
// Cree una nueva instancia de MetafileRenderingOptions
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
    ScaleWmfFontsToMetafileSize = false
};
```

 El`MetafileRenderingOptions` La clase proporciona opciones sobre cómo se representan los metarchivos (como WMF). Configurando`ScaleWmfFontsToMetafileSize` a`false`, le está indicando a Aspose.Words que no escale las fuentes según el tamaño del metarchivo, lo que puede ayudar a reducir el tamaño general del PDF.

## Paso 3: configurar las opciones de guardar PDF

Ahora, configure las opciones de guardado de PDF para usar las opciones de representación de metarchivos que acaba de configurar. Esto le indica a Aspose.Words cómo manejar metarchivos al guardar el documento como PDF.

```csharp
// Cree una nueva instancia de PdfSaveOptions
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    MetafileRenderingOptions = metafileRenderingOptions
};
```

 El`PdfSaveOptions` La clase le permite especificar varias configuraciones para guardar el documento como PDF. Asignando el previamente configurado`MetafileRenderingOptions` hacia`MetafileRenderingOptions` propiedad de`PdfSaveOptions`, se asegura de que el documento se guarde de acuerdo con la configuración de representación del metarchivo deseada.

## Paso 4: guarde el documento como PDF

Finalmente, guarde el documento de Word como PDF usando las opciones de guardado configuradas. Esto aplicará todas las configuraciones, incluidas las opciones de representación de metarchivos, al PDF de salida.


```csharp
// Guarde el documento como PDF
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

 En este paso, el`Save` método de la`Document` La clase se utiliza para exportar el documento a un archivo PDF. Se especifica la ruta donde se guardará el PDF, junto con el`PdfSaveOptions` que incluyen la configuración de representación del metarchivo.

## Conclusión

Al escalar las fuentes WMF al tamaño de un metarchivo, puede reducir significativamente el tamaño de sus archivos PDF generados a partir de documentos de Word. Esta técnica ayuda a optimizar el almacenamiento y la distribución de documentos sin comprometer la calidad del contenido visual. Seguir los pasos descritos anteriormente garantiza que sus archivos PDF sean más manejables y eficientes en tamaño.

## Preguntas frecuentes

### ¿Qué es WMF y por qué es importante para el tamaño del PDF?

WMF (Metarchivo de Windows) es un formato gráfico utilizado en Microsoft Windows. Puede contener datos tanto vectoriales como de mapas de bits. Dado que los datos vectoriales se pueden escalar y manipular, es importante manejarlos adecuadamente para evitar archivos PDF innecesariamente grandes.

### ¿Cómo afecta al PDF el escalado de fuentes WMF al tamaño de metarchivo?

Escalar las fuentes WMF al tamaño de un metarchivo puede ayudar a reducir el tamaño general del PDF al evitar la representación de fuentes de alta resolución que podrían aumentar el tamaño del archivo.

### ¿Puedo utilizar otros formatos de metarchivo con Aspose.Words?

Sí, Aspose.Words admite varios formatos de metarchivos, incluido EMF (Enhanced Metafile) además de WMF.

### ¿Esta técnica es aplicable a todo tipo de documentos de Word?

Sí, esta técnica se puede aplicar a cualquier documento de Word que contenga gráficos WMF, lo que ayuda a optimizar el tamaño del PDF generado.

### ¿Dónde puedo encontrar más información sobre Aspose.Words?

 Puedes explorar más sobre Aspose.Words en el[Documentación de Aspose.Words](https://reference.aspose.com/words/net/) . Para descargas, pruebas y soporte, visite el[Página de descarga de Aspose.Words](https://releases.aspose.com/words/net/), [Comprar Aspose.Words](https://purchase.aspose.com/buy), [Prueba gratis](https://releases.aspose.com/), [Licencia Temporal](https://purchase.aspose.com/temporary-license/) , y[Apoyo](https://forum.aspose.com/c/words/8).