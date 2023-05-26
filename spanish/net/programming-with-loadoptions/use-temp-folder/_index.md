---
title: Usar carpeta temporal
linktitle: Usar carpeta temporal
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar una carpeta temporal al cargar documentos con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-loadoptions/use-temp-folder/
---

Al trabajar con documentos de Word en una aplicación de C#, puede que sea necesario utilizar una carpeta temporal para almacenar archivos temporales generados durante el procesamiento de documentos. Con la biblioteca Aspose.Words para .NET, puede especificar fácilmente una carpeta temporal mediante las opciones de carga de LoadOptions. En esta guía paso a paso, le mostraremos cómo usar Aspose.Words para el código fuente de .NET C# para cargar un documento usando una carpeta temporal especificada usando las opciones de carga de LoadOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Configuración de las opciones de carga

El primer paso es configurar las opciones de carga de nuestro documento. Utilice la clase LoadOptions para especificar los parámetros de carga. En nuestro caso, debemos establecer la propiedad TempFolder en la ruta de la carpeta temporal deseada. Aquí está cómo hacerlo:

```csharp
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };
```

Creamos un nuevo objeto LoadOptions y establecemos la propiedad TempFolder en la ruta de la carpeta temporal deseada.

## Cargue el documento usando la carpeta temporal especificada

Ahora que hemos configurado las opciones de carga, podemos cargar el documento usando la clase Document y especificar las opciones de carga. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

En este ejemplo, cargamos el documento "Documento.docx" ubicado en el directorio de documentos usando las opciones de carga especificadas.

### Código fuente de ejemplo para LoadOptions con la funcionalidad "Usar carpeta temporal" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure las opciones de carga con la función "Usar carpeta temporal"
LoadOptions loadOptions = new LoadOptions { TempFolder = ArtifactsDir };

// Cargue el documento utilizando una carpeta temporal especificada
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

## Conclusión

En esta guía, explicamos cómo cargar un documento usando una carpeta temporal específica usando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. El uso de una carpeta temporal permite que los archivos temporales generados durante el procesamiento de documentos se almacenen de manera organizada y eficiente.
