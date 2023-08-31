---
title: Establecer la versión de MS Word
linktitle: Establecer la versión de MS Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a cargar un documento con una versión específica de MS Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-loadoptions/set-ms-word-version/
---
Cuando se procesa Words con documentos de Word en una aplicación C#, puede ser necesario especificar la versión de Microsoft Word que se usará al cargar el documento. Con la biblioteca Aspose.Words para .NET, puede configurar fácilmente qué versión de MS Word usar usando LoadOptions. En esta guía paso a paso, le explicaremos cómo utilizar Aspose.Words para el código fuente .NET C# para cargar un documento con una versión específica de MS Word utilizando las opciones de carga LoadOptions.

## Comprender la biblioteca Aspose.Words

Antes de profundizar en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluido .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar formato, agregar secciones y mucho más.

## Configurar opciones de carga

El primer paso es configurar las opciones de carga de nuestro documento. Utilice la clase LoadOptions para especificar los parámetros de carga. En nuestro caso, necesitamos configurar la propiedad MswVersion en la versión deseada de MS Word. Por ejemplo, estamos usando la versión Microsoft Word 2010. Aquí se explica cómo hacerlo:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Creamos un nuevo objeto LoadOptions y configuramos la propiedad MswVersion en MsWordVersion.Word2010 para especificar la versión de MS Word 2010.

## Carga de documentos con la versión especificada de MS Word

Ahora que hemos configurado las opciones de carga, podemos cargar el documento usando la clase Documento y especificar las opciones de carga. Aquí hay un ejemplo :

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

// guardar el documento
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Conclusión

En esta guía, explicamos cómo cargar un documento que especifica una versión específica de MS Word utilizando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y utiliza el código fuente C# proporcionado, puede aplicar fácilmente esta funcionalidad en su aplicación C#. Cargar un documento con una versión específica de MS Word le permite garantizar la compatibilidad y el procesamiento adecuados del documento en su aplicación.


### Preguntas frecuentes

#### P: ¿Por qué necesitaría especificar la versión de MS Word al cargar un documento en una aplicación C#?

Especificar la versión de MS Word garantiza que el documento se cargue y procese correctamente, especialmente cuando se trata de formatos específicos o características que pueden variar entre diferentes versiones.

#### P: ¿Qué versiones de MS Word admite Aspose.Words?

R: Aspose.Words para .NET admite varias versiones de MS Word, incluidas Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019 y más.

#### P: ¿Puedo cargar un documento con una versión de MS Word diferente a la instalada en mi sistema?

R: Sí, Aspose.Words le permite especificar una versión diferente de MS Word al cargar el documento, lo que garantiza la compatibilidad incluso si el sistema de destino tiene una versión diferente de MS Word.

#### P: ¿Cómo beneficia la configuración de la versión de MS Word a mi aplicación C#?

R: Configurar la versión de MS Word garantiza que el documento se procese de acuerdo con el formato y las características previstos de esa versión específica, lo que proporciona resultados consistentes.

#### P: ¿Aspose.Words se limita a manejar únicamente documentos DOCX?

R: No, Aspose.Words admite varios formatos de documentos, incluidos DOC, RTF, HTML, PDF y más, lo que lo convierte en una herramienta versátil para manejar diferentes tipos de documentos.