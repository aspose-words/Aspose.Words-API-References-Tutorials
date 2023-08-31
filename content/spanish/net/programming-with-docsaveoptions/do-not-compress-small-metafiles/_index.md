---
title: No comprimir metarchivos pequeños
linktitle: No comprimir metarchivos pequeños
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a utilizar Aspose.Words para .NET para habilitar la función No comprimir metarchivos pequeños al guardar documentos.
type: docs
weight: 10
url: /es/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

La compresión de metadatos en un documento es una característica común cuando se procesa Words con archivos en una aplicación C#. Sin embargo, puede que sea necesario no comprimir los metadatos de archivos pequeños para preservar su calidad. En esta guía paso a paso, le mostraremos cómo utilizar el código fuente C# de Aspose.Words para .NET para habilitar la función "No comprimir metarchivos pequeños" en las opciones de guardar documentos.

## Comprender la biblioteca Aspose.Words

Antes de profundizar en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluido .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar formato, agregar secciones y mucho más.

## Paso 1: configurar el directorio de documentos

El primer paso es definir el directorio donde desea guardar el documento. Debe especificar la ruta completa del directorio. Por ejemplo :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Asegúrese de reemplazar "SU DIRECTORIO DE DOCUMENTOS" con la ruta real a su directorio de documentos.

## Paso 2: Insertar secciones y texto

Luego puede insertar secciones y texto en su documento. Utilice la clase DocumentBuilder proporcionada por Aspose.Words para crear el contenido de su documento. Aquí hay un ejemplo simple:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

En este ejemplo, creamos un nuevo documento en blanco y luego usamos DocumentBuilder para agregar una línea de texto.

## Paso 3: Opciones de configuración

'registro

Ahora configuremos las opciones de guardado de nuestro documento. Utilice la clase DocSaveOptions para especificar la configuración de guardado. Por ejemplo :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

En este ejemplo, estamos creando un nuevo objeto DocSaveOptions para configurar las opciones de guardado.

## Paso 4: habilite la función "No comprimir metarchivos pequeños"

 Para habilitar la función "No comprimir metarchivos pequeños", debe configurar el`Compliance` propiedad del objeto DocSaveOptions al valor`PdfCompliance.PdfA1a`. Así es cómo:

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

Esta configuración garantiza que los metadatos de archivos pequeños no se compriman cuando se guarda el documento.

## Paso 5: guarde el documento

Finalmente, puede guardar el documento usando el`Save` método de la clase Documento. Especifique la ruta completa al archivo y el nombre del archivo deseado. Por ejemplo :

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

Asegúrese de reemplazar "dataDir" con la ruta a su directorio de documentos.

### Código fuente de ejemplo para DocSaveOptions con la función No comprimir metarchivos pequeños usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Inserte dos secciones con algo de texto.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Configure las opciones de guardado con la función "No comprimir metarchivos pequeños"
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// Guarde el documento con las opciones especificadas.
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## Conclusión

En esta guía, explicamos cómo utilizar la biblioteca Aspose.Words para .NET para habilitar la función "No comprimir metarchivos pequeños" al guardar un documento. Si sigue los pasos proporcionados y utiliza el código fuente de C# proporcionado, puede aplicar fácilmente esta funcionalidad en su aplicación C#. Preservar los metadatos de archivos pequeños sin comprimir puede ser importante para mantener la calidad e integridad de los documentos.