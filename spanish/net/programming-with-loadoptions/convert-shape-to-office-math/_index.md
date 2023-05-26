---
title: Convertir forma en matemáticas de Office
linktitle: Convertir forma en matemáticas de Office
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a convertir formas en fórmulas matemáticas de Office al cargar documentos con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-loadoptions/convert-shape-to-office-math/
---

Cuando trabaje con documentos que contienen formas matemáticas en una aplicación de C#, es posible que deba convertirlos a fórmulas matemáticas de Office para mejorar la compatibilidad y la presentación. Con la biblioteca Aspose.Words para .NET, puede convertir fácilmente formas en fórmulas matemáticas de Office mientras carga un documento. En esta guía paso a paso, lo guiaremos a través de cómo usar Aspose.Words para el código fuente de .NET C# para cargar un documento con la conversión de formas en fórmulas matemáticas de Office usando LoadOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Configuración de opciones de carga

El primer paso es configurar las opciones de carga de nuestro documento. Utilice la clase LoadOptions para especificar los parámetros de carga. En nuestro caso, queremos convertir las formas en fórmulas matemáticas de Office, por lo que debemos establecer la propiedad ConvertShapeToOfficeMath en verdadero. Aquí está cómo hacerlo:

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

Creamos un nuevo objeto LoadOptions y establecemos la propiedad ConvertShapeToOfficeMath en true para habilitar la conversión de formas a fórmulas matemáticas de Office al cargar el documento.

## Carga de documentos con conversión de formas a fórmulas matemáticas de Office

Ahora que hemos configurado las opciones de carga, podemos cargar el documento usando la clase Document y especificar las opciones de carga. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

En este ejemplo, cargamos el documento "Office math.docx" ubicado en el directorio de documentos usando las opciones de carga especificadas.

## Registro del documento

Después de cargar el documento con la conversión de formas a fórmulas matemáticas de Office, puede guardarlo en el formato deseado utilizando el método Guardar de la clase Documento. Por ejemplo, para guardar el documento en formato .docx:

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

Asegúrese de reemplazar "dataDir" con la ruta del directorio a sus documentos.

### Ejemplo de código fuente para LoadOptions con la funcionalidad "Convertir forma en Office Math" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Configuración de las opciones de carga con la funcionalidad "Convertir Forma"

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

// Cargue el documento con las opciones especificadas
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

//Guarde el documento en el formato deseado
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## Conclusión

En esta guía, explicamos cómo cargar un documento con la conversión de formas a fórmulas matemáticas de Office usando la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. La conversión de formas en fórmulas matemáticas de Office proporciona una mejor compatibilidad y presentación de documentos que contienen elementos matemáticos.
