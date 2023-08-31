---
title: Obtener sustitución sin sufijos
linktitle: Obtener sustitución sin sufijos
second_title: API de procesamiento de documentos Aspose.Words
description: En este tutorial, aprenderá cómo obtener anulaciones sin sufijo en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/get-substitution-without-suffixes/
---

En este tutorial, le mostraremos cómo obtener anulaciones sin sufijos en un documento de Word utilizando la biblioteca Aspose.Words para .NET. Las sustituciones sin sufijos se utilizan para resolver problemas de sustitución de fuentes al mostrar o imprimir documentos. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#.
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: definir el directorio de documentos
 Primero, debe configurar la ruta del directorio a la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta apropiada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargar el documento y configurar sustituciones sin sufijos
 A continuación, cargaremos el documento usando el`Document` clase y configurar sustituciones sin sufijo utilizando el`DocumentSubstitutionWarnings` clase. También agregaremos una fuente de fuente especificando una carpeta que contenga las fuentes.

```csharp
// Cargar el documento y configurar sustituciones sin sufijos
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Paso 3: guarde el documento
Finalmente, guardaremos el documento con las anulaciones sin sufijo aplicadas.

```csharp
// guardar el documento
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Código fuente de muestra para obtener sustitución sin sufijos usando Aspose.Words para .NET 
```csharp

//Ruta a su directorio de documentos
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
En este tutorial, vimos cómo obtener anulaciones sin sufijos en un documento de Word con Aspose.Words para .NET. Las sustituciones sin sufijos son útiles para resolver problemas de sustitución de fuentes. No dude en utilizar esta función para mejorar la visualización y la impresión de sus documentos.

### Preguntas frecuentes

#### P: ¿Por qué Aspose.Words agrega sufijos a las sustituciones de fuentes?

R: Aspose.Words agrega sufijos a las sustituciones de fuentes para evitar conflictos entre las fuentes originales y las fuentes sustituidas. Esto ayuda a garantizar la máxima compatibilidad al convertir y manipular documentos.

#### P: ¿Cómo puedo recuperar sustituciones de fuentes sin sufijos en Aspose.Words?

 R: Para recuperar sustituciones de fuentes sin sufijos en Aspose.Words, puede utilizar el`FontSubstitutionSettings` clase y el`RemoveSuffixes` propiedad. Estableciendo esta propiedad en`true` Obtendrá las sustituciones de fuentes sin los sufijos agregados.

#### P: ¿Es posible desactivar la adición de sufijos a las sustituciones de fuentes en Aspose.Words?

R: No, no es posible desactivar la adición de sufijos a las sustituciones de fuentes en Aspose.Words. Los sufijos se agregan de forma predeterminada para garantizar la compatibilidad y coherencia del documento.

#### P: ¿Cómo puedo filtrar sufijos no deseados en las sustituciones de fuentes en Aspose.Words?

 R: Para filtrar sufijos no deseados en sustituciones de fuentes en Aspose.Words, puede utilizar técnicas de procesamiento de cadenas, como el uso de`Replace` o`Substring` métodos para eliminar sufijos específicos que no desea incluir.