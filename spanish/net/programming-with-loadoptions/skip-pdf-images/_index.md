---
title: Saltar imágenes en PDF
linktitle: Saltar imágenes en PDF
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a cargar un documento PDF sin cargar imágenes PDF con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-loadoptions/skip-pdf-images/
---

Cuando se trabaja con documentos PDF en una aplicación C#, puede que sea necesario omitir la carga de imágenes PDF por motivos de rendimiento o de gestión del espacio de almacenamiento. Con la biblioteca Aspose.Words para .NET, puede omitir fácilmente la carga de imágenes PDF utilizando las opciones de carga de PdfLoadOptions. En esta guía paso a paso, lo guiaremos a través de cómo usar Aspose.Words para el código fuente de .NET C# para cargar un documento PDF omitiendo la carga de imágenes PDF usando las opciones de carga de PdfLoadOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Configuración de las opciones de carga

El primer paso es configurar las opciones de carga de nuestro documento PDF. Utilice la clase PdfLoadOptions para especificar los parámetros de carga. En nuestro caso, debemos establecer la propiedad SkipPdfImages en verdadero para omitir la carga de imágenes PDF. Aquí está cómo hacerlo:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };
```

Creamos un nuevo objeto PdfLoadOptions y establecemos la propiedad SkipPdfImages en true para omitir la carga de imágenes PDF.

## Cargar documento PDF saltando imágenes PDF

Ahora que hemos configurado las opciones de carga, podemos cargar el documento PDF utilizando la clase Documento y especificar las opciones de carga. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

En este ejemplo, estamos cargando el documento PDF "Pdf Document.pdf" ubicado en el directorio de documentos usando las opciones de carga especificadas.

### Ejemplo de código fuente para PdfLoadOptions con la funcionalidad "Omitir imágenes en PDF" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure las opciones de carga con la función "Omitir imágenes en PDF"
PdfLoadOptions loadOptions = new PdfLoadOptions { SkipPdfImages = true };

// Cargue el documento PDF saltándose las imágenes PDF
Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

## Conclusión

En esta guía, explicamos cómo cargar un documento PDF omitiendo la carga de imágenes PDF utilizando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. Omitir la carga de imágenes PDF puede mejorar el rendimiento y la gestión del espacio de almacenamiento al procesar documentos PDF.