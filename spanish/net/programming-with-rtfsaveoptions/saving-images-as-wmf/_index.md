---
title: Guardar imágenes como Wmf
linktitle: Guardar imágenes como Wmf
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a guardar imágenes como WMF al convertirlas a RTF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

En este tutorial, exploraremos el código fuente de C# proporcionado para la función "Guardar imágenes como WMF con opciones de guardado RTF" con Aspose.Words para .NET. Esta función le permite guardar imágenes de documentos en formato de metarchivo de Windows (WMF) al convertir a formato RTF.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: Cargar el documento

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 En este paso, cargamos el documento usando el`Document` método y pasando la ruta al archivo DOCX para cargar.

## Paso 3: Configuración de las opciones de copia de seguridad

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

En este paso, configuramos las opciones de copia de seguridad RTF. Creamos un nuevo`RtfSaveOptions` objeto y establecer el`SaveImagesAsWmf` propiedad a`true`. Esto le dice a Aspose.Words que guarde las imágenes del documento como WMF al convertirlas a RTF.

## Paso 4: Guardar el documento

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

 En este último paso, guardamos el documento resultante en formato RTF utilizando el`Save` y pasando la ruta al archivo de salida, junto con las opciones de guardado especificadas.

Ahora puede ejecutar el código fuente para guardar imágenes de documentos en formato WMF mientras convierte a formato RTF. El documento resultante se guardará en el directorio especificado con el nombre "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf".

### Ejemplo de código fuente para la funcionalidad de guardar imágenes WMF con opciones de guardado RTF con Aspose.Words para .NET".

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## Conclusión

En este tutorial, exploramos la funcionalidad de guardar imágenes como WMF con opciones de guardado RTF en Aspose.Words para .NET. Aprendimos cómo guardar imágenes de un documento en formato WMF al convertirlo a formato RTF.

Esta característica es útil cuando desea mantener la calidad y resolución de las imágenes en sus documentos RTF. Al guardar imágenes en formato WMF, puede asegurarse de que su apariencia y nitidez permanezcan intactas.

Aspose.Words para .NET ofrece muchas características avanzadas para la manipulación y generación de documentos. Guardar imágenes en formato WMF mientras se convierte a formato RTF es una de las muchas herramientas poderosas que le brinda.