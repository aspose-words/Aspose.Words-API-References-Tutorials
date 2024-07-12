---
title: Obtener lista de fuentes disponibles
linktitle: Obtener lista de fuentes disponibles
second_title: API de procesamiento de documentos Aspose.Words
description: En este tutorial, aprenderá cómo obtener la lista de fuentes disponibles en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/get-list-of-available-fonts/
---
En este tutorial, explicaremos cómo obtener la lista de fuentes disponibles en Aspose.Words para .NET. La lista de fuentes disponibles le permite saber qué fuentes puede utilizar en sus documentos. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

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

## Paso 2: configurar las fuentes de fuentes
 continuación, crearemos una instancia de`FontSettings` y obtener las fuentes de fuentes existentes utilizando el`GetFontsSources()` método. También agregaremos una nueva fuente de fuente especificando una carpeta que contenga fuentes.

```csharp
// Configurar fuentes de fuentes
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Agregar una nueva fuente de fuente
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Paso 3: obtenga la lista de fuentes disponibles
 Ahora exploraremos las fuentes disponibles usando el`GetAvailableFonts()` método en la primera fuente de fuente actualizada.

```csharp
// Obtener la lista de fuentes disponibles
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Código fuente de muestra para obtener una lista de fuentes disponibles usando Aspose.Words para .NET 

```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Agregue una nueva fuente de carpeta que le indicará a Aspose.Words que busque fuentes en la siguiente carpeta.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Agregue la carpeta personalizada que contiene nuestras fuentes a la lista de fuentes de fuentes existentes.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Conclusión
En este tutorial, vimos cómo obtener la lista de fuentes disponibles en Aspose.Words para .NET. Esto le permite saber qué fuentes puede utilizar en sus documentos. No dude en utilizar esta función para elegir las fuentes adecuadas a sus necesidades.

### Preguntas frecuentes

#### P: ¿Cómo puedo recuperar la lista de fuentes disponibles en Aspose.Words?

 R: Para recuperar la lista de fuentes disponibles en Aspose.Words, puede utilizar el`FontsProvider` clase y el`GetAvailableFonts` método. Este método devolverá una lista de todas las fuentes instaladas en su sistema.

#### P: ¿Puedo filtrar la lista de fuentes disponibles según ciertos criterios en Aspose.Words?

R: Sí, puedes filtrar la lista de fuentes disponibles en Aspose.Words usando criterios específicos. Por ejemplo, puedes filtrar fuentes por familia, estilo o idioma.

#### P: ¿Cómo puedo utilizar la lista de fuentes disponibles en mis documentos de Word?

 R: Para usar la lista de fuentes disponibles en sus documentos de Word, puede explorar la lista y seleccionar las fuentes apropiadas usando los métodos y propiedades del`FontSettings` clase en Aspose.Words.