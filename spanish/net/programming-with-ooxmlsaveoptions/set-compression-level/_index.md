---
title: Establecer nivel de compresión
linktitle: Establecer nivel de compresión
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a configurar el nivel de compresión al guardar un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
En este tutorial, exploraremos el código fuente de C# proporcionado para establecer el nivel de compresión al guardar un documento con Aspose.Words para .NET. Esta característica le permite controlar el nivel de compresión del documento generado.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: Cargar el documento

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 En este paso, cargamos el documento usando el`Document` método y pasando la ruta al archivo DOCX para cargar.

## Paso 3: Configuración de las opciones de copia de seguridad de OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

 En este paso, configuramos las opciones de guardado de OOXML usando el`OoxmlSaveOptions` clase. Establecemos el nivel de compresión en`SuperFast` para obtener una compresión más rápida.

## Paso 4: Guarde el documento con el nivel de compresión especificado

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

 En este último paso, guardamos el documento usando el`Save` y pasando la ruta al archivo de salida con el`.docx` extensión, junto con las opciones de guardado especificadas.

Ahora puede ejecutar el código fuente para establecer el nivel de compresión al guardar un documento. El archivo resultante se guardará en el directorio especificado con el nombre "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx".

### Ejemplo de código fuente para establecer el nivel de compresión con Aspose.Words para .NET 

```csharp

//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## Conclusión

En este tutorial, exploramos la funcionalidad de configurar el nivel de compresión al guardar un documento usando Aspose.Words para .NET. Al especificar el nivel adecuado de compresión, puede optimizar el tamaño del documento y la velocidad de generación.

 El`OoxmlSaveOptions`La clase proporciona flexibilidad para controlar el nivel de compresión configurando el`CompressionLevel` propiedad a un valor apropiado, tal como`SuperFast`. Esto le permite lograr el equilibrio adecuado entre el tamaño del archivo y la velocidad de la copia de seguridad en función de sus necesidades específicas.

El uso de la compresión puede ser beneficioso cuando necesita reducir el tamaño de los archivos generados, especialmente para documentos grandes. Esto puede facilitar el almacenamiento, el intercambio y la transmisión de documentos.

Aspose.Words para .NET ofrece una gama de potentes opciones y características para la manipulación de documentos. Mediante el uso de las opciones de copia de seguridad adecuadas, puede personalizar el proceso de generación de documentos y optimizar el rendimiento de su aplicación.

Siéntase libre de explorar más características de Aspose.Words para .NET para mejorar su flujo de trabajo de generación de documentos.
