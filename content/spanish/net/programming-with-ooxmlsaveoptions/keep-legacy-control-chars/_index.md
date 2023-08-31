---
title: Conservar caracteres de control heredados
linktitle: Conservar caracteres de control heredados
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a conservar los caracteres de control heredados al guardar un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

En este tutorial, exploraremos el código fuente de C# proporcionado para conservar los caracteres de control heredados al guardar un documento con Aspose.Words para .NET. Esta función le permite conservar caracteres de control especiales al convertir o guardar un documento.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: Cargar el documento

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 En este paso, cargamos el documento usando el`Document` y pasando la ruta al archivo que contiene los caracteres de control heredados.

## Paso 3: Configuración de las opciones de copia de seguridad de OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

En este paso, configuramos las opciones de guardado de OOXML creando un nuevo`OoxmlSaveOptions`objeto. Especificamos el formato de guardado deseado (aquí,`FlatOpc` ) y habilite la`KeepLegacyControlChars` opción para mantener los caracteres de control heredados.

## Paso 4: Guardar el documento con caracteres de control heredados

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 En este último paso, guardamos el documento usando el`Save` y pasando la ruta al archivo de salida con el`.docx` extensión, junto con las opciones de guardado especificadas.

Ahora puede ejecutar el código fuente para conservar los caracteres de control heredados al guardar un documento. El archivo resultante se guardará en el directorio especificado con el nombre "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Ejemplo de código fuente para Keep Legacy Control Chars usando Aspose.Words para .NET 
```csharp

//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Conclusión

En este tutorial, exploramos la funcionalidad de conservar los caracteres de control heredados al guardar un documento con Aspose.Words para .NET. Hemos aprendido a conservar esos caracteres especiales que pueden ser importantes para el formato o la visualización adecuados del documento.

 Conservar los caracteres de control heredados es especialmente útil cuando se utiliza el procesamiento de textos con documentos que utilizan funciones más antiguas o específicas, como los caracteres de control especiales. Al habilitar el`KeepLegacyControlChars`opción al guardar el documento, se asegura de que se conserven estos caracteres.

Aspose.Words para .NET ofrece una gama de opciones de respaldo flexibles y potentes para satisfacer sus necesidades de manipulación de documentos. Mediante el uso de las opciones adecuadas, puede personalizar el proceso de copia de seguridad para conservar las características específicas de sus documentos.

Siéntase libre de incorporar esta funcionalidad en sus proyectos Aspose.Words para .NET para garantizar la integridad y preservación de los caracteres de control heredados en sus documentos.