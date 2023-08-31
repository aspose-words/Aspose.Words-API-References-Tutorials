---
title: Mantener caracteres de control heredados
linktitle: Mantener caracteres de control heredados
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo conservar los caracteres de control heredados al guardar un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

En este tutorial, exploraremos el código fuente de C# proporcionado para preservar los caracteres de control heredados al guardar un documento usando Aspose.Words para .NET. Esta función le permite conservar caracteres de control especiales al convertir o guardar un documento.

## Paso 1: configurar el entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: cargar el documento

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 En este paso, cargamos el documento usando el`Document` método y pasando la ruta al archivo que contiene los caracteres de control heredados.

## Paso 3: configurar las opciones de copia de seguridad de OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

En este paso, configuramos las opciones de guardado de OOXML creando un nuevo`OoxmlSaveOptions`objeto. Especificamos el formato de guardado deseado (aquí,`FlatOpc` ) y habilitar el`KeepLegacyControlChars` Opción para mantener los personajes de control heredados.

## Paso 4: guardar el documento con caracteres de control heredados

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 En este último paso guardamos el documento utilizando el`Save` método y pasando la ruta al archivo de salida con el`.docx` extensión, junto con las opciones de guardado especificadas.

Ahora puede ejecutar el código fuente para conservar los caracteres de control heredados al guardar un documento. El archivo resultante se guardará en el directorio especificado con el nombre "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Código fuente de muestra para Keep Legacy Control Chars usando Aspose.Words para .NET 
```csharp

//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Conclusión

En este tutorial, exploramos la funcionalidad de preservar los caracteres de control heredados al guardar un documento usando Aspose.Words para .NET. Hemos aprendido cómo conservar esos caracteres especiales que pueden ser importantes para formatear o visualizar correctamente el documento.

 Preservar los caracteres de control heredados es especialmente útil cuando se procesan palabras con documentos que utilizan funciones antiguas o específicas, como caracteres de control especiales. Al habilitar el`KeepLegacyControlChars`Al guardar el documento, se asegura de que estos caracteres se conserven.

Aspose.Words para .NET ofrece una gama de opciones de copia de seguridad potentes y flexibles para satisfacer sus necesidades de manipulación de documentos. Al utilizar las opciones adecuadas, puede personalizar el proceso de copia de seguridad para preservar las características específicas de sus documentos.

No dude en incorporar esta funcionalidad en sus proyectos Aspose.Words para .NET para garantizar la integridad y preservación de los caracteres de control heredados en sus documentos.