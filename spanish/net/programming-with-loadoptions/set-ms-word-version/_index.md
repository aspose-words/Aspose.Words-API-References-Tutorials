---
title: Establecer la versión de MS Word
linktitle: Establecer la versión de MS Word
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a cargar un documento con una versión específica de MS Word utilizando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-loadoptions/set-ms-word-version/
---

Al trabajar con documentos de Word en una aplicación C#, puede ser necesario especificar la versión de Microsoft Word que se utilizará al cargar el documento. Con la biblioteca Aspose.Words para .NET, puede establecer fácilmente qué versión de MS Word usar mediante LoadOptions. En esta guía paso a paso, lo guiaremos a través de cómo usar Aspose.Words para el código fuente de .NET C# para cargar un documento con una versión específica de MS Word usando las opciones de carga de LoadOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Configuración de opciones de carga

El primer paso es configurar las opciones de carga de nuestro documento. Utilice la clase LoadOptions para especificar los parámetros de carga. En nuestro caso, debemos establecer la propiedad MswVersion en la versión deseada de MS Word. Por ejemplo, estamos usando la versión de Microsoft Word 2010. Aquí está cómo hacerlo:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Creamos un nuevo objeto LoadOptions y establecemos la propiedad MswVersion en MsWordVersion.Word2010 para especificar la versión de MS Word 2010.

## Carga de documentos con la versión especificada de MS Word

Ahora que hemos configurado las opciones de carga, podemos cargar el documento usando la clase Document y especificar las opciones de carga. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

En este ejemplo, cargamos el documento "Documento.docx" ubicado en el directorio de documentos usando las opciones de carga especificadas.

### Código fuente de ejemplo para LoadOptions con la funcionalidad "Establecer versión de MS Word" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configure las opciones de carga con la función "Establecer versión de MS Word"
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Cargue el documento con la versión especificada de MS Word
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Guardar el documento
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Conclusión

En esta guía, explicamos cómo cargar un documento que especifica una versión específica de MS Word utilizando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. Cargar un documento con una versión específica de MS Word le permite garantizar la compatibilidad y el procesamiento adecuados del documento en su aplicación.
