---
title: No guardar viñeta de imagen
linktitle: No guardar viñeta de imagen
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a deshabilitar el guardado de viñetas de imágenes en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Las viñetas de imagen son una característica de uso común en los documentos de Word para agregar viñetas personalizadas. Sin embargo, en algunos casos puede ser necesario deshabilitar el registro de viñetas de imágenes cuando se manipulan documentos usando Aspose.Words Library para .NET. En esta guía paso a paso, explicaremos cómo usar el código fuente de Aspose.Words C# para .NET para deshabilitar el guardado de viñetas de imágenes usando las opciones de guardado de DocSaveOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Paso 1: Configuración del directorio de documentos

El primer paso es definir el directorio donde se encuentran sus documentos. Debe especificar la ruta completa del directorio. Por ejemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 2: cargar el documento con viñetas de imagen

A continuación, debe cargar el documento con viñetas de imagen. Utilice la clase Document para cargar el documento desde un archivo. Por ejemplo :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

En este ejemplo estamos cargando el documento desde el archivo "Imagen viñetas.docx"

  ubicado en el directorio de documentos.

## Paso 3: Configure las opciones de grabación

Ahora vamos a configurar las opciones de guardado de nuestro documento. Utilice la clase DocSaveOptions para especificar la configuración de guardado. Por ejemplo :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

En este ejemplo, creamos un nuevo objeto DocSaveOptions y establecemos la propiedad SavePictureBullet en falso para deshabilitar el guardado de viñetas de imágenes.

## Paso 4: habilite la función "No guardar viñeta de imagen"

Para habilitar la función "No guardar viñeta de imagen", ya hemos configurado las opciones de guardado con SavePictureBullet establecido en falso. Esto garantiza que las viñetas de imagen no se guarden en el documento final.

## Paso 5: Guarde el documento

Finalmente, puede guardar el documento utilizando el método Guardar de la clase Documento. Especifique la ruta completa al archivo y el nombre de archivo deseado. Por ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Asegúrese de reemplazar "dataDir" con la ruta del directorio a sus documentos.

## Código fuente de ejemplo para las opciones de guardado de DocSaveOptions con la funcionalidad "No guardar viñeta de imagen" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento con viñetas de imagen
Document doc = new Document(dataDir + "Image bullet points.docx");

// Configure las opciones de guardado con la función "No guardar la viñeta de imagen"
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Guarde el documento con las opciones especificadas
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Conclusión

En esta guía, cubrimos cómo deshabilitar el guardado de viñetas de imágenes en un documento usando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. Deshabilitar el guardado de viñetas de imágenes puede ser útil en algunas situaciones para conservar la estructura y el formato del documento sin guardar las viñetas de imágenes.