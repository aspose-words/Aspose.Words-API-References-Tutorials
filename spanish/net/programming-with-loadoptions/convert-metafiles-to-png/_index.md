---
title: Convertir metarchivos a png
linktitle: Convertir metarchivos a png
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir metarchivos a imágenes PNG al cargar documentos con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-loadoptions/convert-metafiles-to-png/
---
Cuando se trabaja con documentos en una aplicación C#, puede ser necesario convertir los metarchivos en imágenes PNG para una mejor compatibilidad y una representación precisa. Con la biblioteca Aspose.Words para .NET, puede convertir fácilmente metarchivos a PNG mientras carga un documento. En esta guía paso a paso, lo guiaremos a través de cómo usar Aspose.Words para el código fuente de .NET C# para cargar un documento con la conversión de metarchivos a PNG usando las opciones de carga de LoadOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Paso 1: Definición del directorio de documentos

El primer paso es definir el directorio donde se encuentran sus documentos. Debe especificar la ruta completa del directorio. Por ejemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 2: Configuración de las opciones de carga

Ahora vamos a configurar las opciones de carga de nuestro documento. Utilice la clase LoadOptions para especificar los parámetros de carga. Por ejemplo :

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertMetafilesToPng = true };
```

En este ejemplo, creamos un nuevo objeto LoadOptions y establecemos la propiedad ConvertMetafilesToPng en verdadero para habilitar la conversión de metarchivos a PNG al cargar el documento.

## Paso 3: cargar el documento con la conversión de metarchivos a PNG

Ahora que hemos configurado las opciones de carga, podemos cargar el documento usando la clase Document y especificar las opciones de carga. Por ejemplo :

```csharp
Document doc = new Document(dataDir + "WMF with image.docx", loadOptions);
```

En este ejemplo, estamos cargando el documento "WMF con imagen.docx" ubicado en el directorio de documentos usando las opciones de carga especificadas.

## Ejemplo de código fuente para LoadOptions con la función Convertir metarchivos a png usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure las opciones de carga con la función "Convertir metarchivos a png"
LoadOptions loadOptions = new LoadOptions { ConvertMetafilesToPng = true };

// Cargue el documento con las opciones especificadas
Document doc = new Document(dataDir + "WMF with image.docx", loadOptions);
```

## Conclusión

En esta guía, explicamos cómo cargar un documento con la conversión de metarchivos a imágenes PNG utilizando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. La conversión de metarchivos a PNG garantiza una mejor compatibilidad y una representación precisa de los documentos.
