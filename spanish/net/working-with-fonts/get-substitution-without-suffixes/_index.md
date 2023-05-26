---
title: Obtener sustitución sin sufijos
linktitle: Obtener sustitución sin sufijos
second_title: Referencia de API de Aspose.Words para .NET
description: En este tutorial, aprenda cómo obtener anulaciones sin sufijo en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/get-substitution-without-suffixes/
---

En este tutorial, le mostraremos cómo obtener anulaciones sin sufijos en un documento de Word utilizando la biblioteca Aspose.Words para .NET. Las sustituciones sin sufijos se utilizan para resolver problemas de sustitución de fuentes al mostrar o imprimir documentos. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: Definir el directorio de documentos
 Primero, debe establecer la ruta del directorio en la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento y configure sustituciones sin sufijos
 A continuación, cargaremos el documento usando el`Document` clase y configurar sustituciones sin sufijo usando el`DocumentSubstitutionWarnings` clase. También agregaremos una fuente de fuentes especificando una carpeta que contenga las fuentes.

```csharp
//Cargue el documento y configure sustituciones sin sufijos
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Paso 3: Guarde el documento
Finalmente, guardaremos el documento con las anulaciones sin sufijo aplicadas.

```csharp
// Guardar el documento
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Ejemplo de código fuente para Obtener sustitución sin sufijos mediante Aspose.Words para .NET 
```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Conclusión
En este tutorial, vimos cómo obtener anulaciones sin sufijos en un documento de Word con Aspose.Words para .NET. Las sustituciones sin sufijos son útiles para resolver problemas de sustitución de fuentes. No dude en utilizar esta función para mejorar la visualización e impresión de sus documentos.
