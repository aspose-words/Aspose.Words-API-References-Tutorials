---
title: No guardar viñeta de imagen
linktitle: No guardar viñeta de imagen
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a deshabilitar el guardado de viñetas de imágenes en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Las viñetas de imagen son una característica de uso común en los documentos de Word para agregar viñetas personalizadas. Sin embargo, en algunos casos puede ser necesario desactivar el registro de viñetas de imágenes al manipular documentos utilizando la biblioteca Aspose.Words para .NET. En esta guía paso a paso, explicaremos cómo usar el código fuente de Aspose.Words C# para .NET para deshabilitar el guardado de viñetas de imágenes usando las opciones de guardado de DocSaveOptions.

## Comprender la biblioteca Aspose.Words

Antes de profundizar en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluido .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar formato, agregar secciones y mucho más.

## Paso 1: configurar el directorio de documentos

El primer paso es definir el directorio donde se encuentran sus documentos. Debe especificar la ruta completa del directorio. Por ejemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 2: cargar el documento con viñetas de imagen

A continuación, debe cargar el documento con viñetas de imágenes. Utilice la clase Documento para cargar el documento desde un archivo. Por ejemplo :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

En este ejemplo, estamos cargando el documento desde el archivo "Viñetas de imagen.docx".

  ubicado en el directorio de documentos.

## Paso 3: configurar las opciones de grabación

Ahora configuremos las opciones de guardado de nuestro documento. Utilice la clase DocSaveOptions para especificar la configuración de guardado. Por ejemplo :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

En este ejemplo, creamos un nuevo objeto DocSaveOptions y configuramos la propiedad SavePictureBullet en falso para deshabilitar el guardado de viñetas de imágenes.

## Paso 4: habilite la función "No guardar viñetas de imagen"

Para habilitar la función "No guardar viñetas de imagen", ya hemos configurado las opciones de guardar con SavePictureBullet configurado en falso. Esto garantiza que las viñetas de las imágenes no se guarden en el documento final.

## Paso 5: guarde el documento

Finalmente, puede guardar el documento usando el método Guardar de la clase Documento. Especifique la ruta completa al archivo y el nombre del archivo deseado. Por ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Asegúrese de reemplazar "dataDir" con la ruta del directorio a sus documentos.

## Código fuente de ejemplo para las opciones de guardado de DocSaveOptions con la funcionalidad "No guardar viñetas de imagen" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento con viñetas de imagen.
Document doc = new Document(dataDir + "Image bullet points.docx");

// Configure las opciones para guardar con la función "No guardar viñetas de imagen"
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Guarde el documento con las opciones especificadas.
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Conclusión

En esta guía, cubrimos cómo deshabilitar el guardado de viñetas de imágenes en un documento usando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y utiliza el código fuente de C# proporcionado, puede aplicar fácilmente esta funcionalidad en su aplicación C#. Deshabilitar el guardado de viñetas de imágenes puede resultar útil en algunas situaciones para preservar la estructura y el formato del documento sin guardar viñetas de imágenes.