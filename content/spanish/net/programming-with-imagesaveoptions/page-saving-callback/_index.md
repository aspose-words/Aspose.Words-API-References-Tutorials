---
title: Devolución de llamada para guardar página
linktitle: Devolución de llamada para guardar página
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a personalizar el guardado de páginas de documentos en imágenes con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-imagesaveoptions/page-saving-callback/
---

En este tutorial, exploraremos el código fuente de C# proporcionado para usar la devolución de llamada para guardar la página con las opciones de guardado de imágenes de Aspose.Words para .NET. Esta función le permite realizar acciones personalizadas al guardar cada página de un documento como una imagen.

## Paso 1: configurar el entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: cargar el documento

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 En este paso, cargamos el documento usando el`Document` método y pasando la ruta al archivo DOCX para cargar.

## Paso 3: configurar las opciones de copia de seguridad de imágenes

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 En este paso, configuramos las opciones para guardar la imagen creando una nueva`ImageSaveOptions` objeto. Especificamos el formato de copia de seguridad deseado, aquí "Png" para el formato PNG. Usamos`PageSet` para especificar el rango de páginas a guardar, aquí desde la primera página hasta la última página del documento (`doc.PageCount - 1`). También establecemos`PageSavingCallback` a una instancia de`HandlePageSavingCallback`, que es una clase personalizada para manejar la devolución de llamada para guardar la página.

## Paso 4: Implementar la devolución de llamada para guardar página

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Implemente sus acciones personalizadas aquí
         // Puede acceder a la información de la página a través de la propiedad "args.PageIndex"
         // También puede cambiar las opciones de guardado para cada página individualmente.
     }
}
```

 En este paso implementamos el`HandlePageSavingCallback` clase que implementa el`IPageSavingCallback` interfaz. Puede personalizar esta clase agregando sus acciones específicas en el`PageSaving` método. Puede acceder a la información de la página a través del`args.PageIndex` propiedad de la`PageSavingArgs` objeto pasado como argumento.

## Paso 5: guardar páginas como imágenes

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 En este paso final, guardamos cada página del documento como una imagen usando el`Save` método y pasando la ruta al archivo de salida con el`.png` extensión, junto con las opciones de guardado especificadas.

Ahora puedes ejecutar el código fuente para realizar acciones personalizadas al guardar cada página del documento como una imagen. El archivo resultante se guardará en el directorio especificado con el nombre "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Código fuente de muestra para devolución de llamada para guardar páginas usando Aspose.Words para .NET


```csharp 
//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Conclusión

En este tutorial, exploramos la funcionalidad de devolución de llamada para guardar la página con las opciones de guardado de imágenes de Aspose.Words para .NET. Aprendimos cómo realizar acciones personalizadas al guardar cada página de un documento como una imagen.

Esta función es útil cuando desea realizar operaciones específicas en cada página al convertir a imágenes. Puede acceder a la información de la página y utilizarla para personalizar las opciones de copia de seguridad o realizar otro procesamiento específico de la página.

Aspose.Words para .NET ofrece una amplia gama de funciones avanzadas para la manipulación y generación de documentos. El recordatorio de guardar página es una de las muchas herramientas poderosas que le brinda para personalizar el proceso de guardar páginas en imágenes.