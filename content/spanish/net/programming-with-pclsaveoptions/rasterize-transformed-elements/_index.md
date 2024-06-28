---
title: Rasterizar elementos transformados
linktitle: Rasterizar elementos transformados
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo deshabilitar la rasterización de elementos transformados al convertir al formato PCL con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words para .NET es una poderosa biblioteca para crear, manipular y convertir documentos de Word en una aplicación C#. Entre las características que ofrece Aspose.Words se encuentra la capacidad de rasterizar elementos transformados al convertir documentos a diferentes formatos. En esta guía, le mostraremos cómo utilizar el código fuente C# de Aspose.Words para .NET para deshabilitar la rasterización de elementos transformados al convertir un documento al formato PCL.

## Comprender la biblioteca Aspose.Words

Antes de profundizar en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una biblioteca popular que hace que el procesamiento de palabras con documentos de Word sea fácil y eficiente. Ofrece una amplia gama de funciones para crear, editar y convertir documentos de Word, incluida la compatibilidad con la rasterización de elementos transformados durante la conversión.

## Cargando el documento de Word

El primer paso es cargar el documento de Word que desea convertir al formato PCL. Utilice la clase Documento para cargar el documento desde el archivo fuente. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

En este ejemplo, estamos cargando el documento "Rendering.docx" ubicado en el directorio de documentos.

## Configurar opciones de copia de seguridad

El siguiente paso es configurar las opciones de guardado para convertir al formato PCL. Utilice la clase PclSaveOptions y establezca la propiedad RasterizeTransformedElements en falso. He aquí cómo hacerlo:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

Creamos un nuevo objeto PclSaveOptions y configuramos la propiedad SaveFormat en SaveFormat.Pcl para especificar que queremos guardar el documento en formato PCL. A continuación, configuramos la propiedad RasterizeTransformedElements en falso para deshabilitar la rasterización de elementos transformados.

## Convertir el documento al formato PCL

Ahora que hemos configurado las opciones de guardado, podemos proceder a convertir el documento al formato PCL. Utilice el método Guardar de la clase Documento para guardar el documento convertido en formato PCL especificando opciones de guardado. Aquí hay un ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

En este ejemplo, guardamos el documento convertido como "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" usando las opciones de guardado especificadas.

### Código fuente de ejemplo para la función "Rasterizar elementos transformados" con Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento de Word


Document doc = new Document(dataDir + "Rendering.docx");

// Configure las opciones de copia de seguridad para la conversión al formato PCL
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Convertir el documento a formato PCL
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Conclusión

En esta guía, cubrimos cómo usar Aspose.Words para .NET para deshabilitar la rasterización de elementos transformados al convertir un documento al formato PCL usando el código fuente C# proporcionado. Si sigue los pasos proporcionados, podrá controlar fácilmente el comportamiento de rasterización de los elementos transformados al convertir sus documentos de Word a diferentes formatos. Aspose.Words ofrece una tremenda flexibilidad y poder para trabajar con los elementos transformados, permitiéndole crear documentos convertidos precisamente según sus necesidades específicas.