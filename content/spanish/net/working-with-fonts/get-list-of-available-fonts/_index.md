---
title: Obtener lista de fuentes disponibles
linktitle: Obtener lista de fuentes disponibles
second_title: API de procesamiento de documentos Aspose.Words
description: Descubra cómo obtener una lista de fuentes disponibles usando Aspose.Words para .NET en este tutorial detallado paso a paso. Mejore sus habilidades de administración de fuentes.
type: docs
weight: 10
url: /es/net/working-with-fonts/get-list-of-available-fonts/
---
## Introducción

¿Alguna vez ha tenido dificultades para administrar las fuentes en sus documentos de Word? Si es desarrollador de .NET, ¡Aspose.Words para .NET está aquí para rescatarlo! Esta poderosa biblioteca no solo lo ayuda a crear y manipular documentos de Word mediante programación, sino que también ofrece amplias capacidades de administración de fuentes. En esta guía, lo guiaremos a través de un tutorial paso a paso sobre cómo obtener una lista de fuentes disponibles usando Aspose.Words para .NET. Lo dividiremos en pasos digeribles para asegurarnos de que pueda seguirlos con facilidad. Entonces, ¡profundicemos y hagamos que la administración de fuentes sea muy sencilla!

## Requisitos previos

Antes de comenzar, hay algunas cosas que necesitará:

-  Aspose.Words para .NET: asegúrese de tener instalada la biblioteca Aspose.Words para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/words/net/).
- Visual Studio: este ejemplo utiliza Visual Studio como entorno de desarrollo.
- .NET Framework: asegúrese de tener .NET Framework instalado en su máquina.
- Directorio de documentos: una ruta de directorio donde se almacenan sus documentos.

## Importar espacios de nombres

Primero, importe los espacios de nombres necesarios a su proyecto:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## Paso 1: inicializar la configuración de fuente

El primer paso es inicializar la configuración de fuente. Esto le permitirá administrar las fuentes de fuentes de sus documentos.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- FontSettings: esta clase se utiliza para especificar la configuración para la sustitución de fuentes y las fuentes de fuentes.
- fontSources: Creamos una lista de fuentes de fuentes existentes a partir de la configuración de fuentes actual.

## Paso 2: definir el directorio de documentos

A continuación, especifique la ruta a su directorio de documentos. Aquí es donde Aspose.Words buscará fuentes.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: esta variable de cadena contiene la ruta al directorio donde se encuentran sus fuentes. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con el camino real.

## Paso 3: agregar una carpeta de fuentes personalizadas

Ahora, agregue una nueva fuente de carpeta para indicarle a Aspose.Words que busque fuentes en esta carpeta.

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource: esta clase representa una fuente de fuente de carpeta. El segundo parámetro (`true`) indica si se deben buscar fuentes de forma recursiva en subcarpetas.

## Paso 4: actualice las fuentes de fuentes

Agregue la carpeta de fuentes personalizadas a la lista de fuentes de fuentes existentes y actualice la configuración de fuentes.

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- fontSources.Add(folderFontSource): agrega la carpeta de fuentes personalizadas a las fuentes de fuentes existentes.
- updateFontSources: convierte la lista de fuentes de fuentes en una matriz.

## Paso 5: recuperar y mostrar fuentes

Finalmente, recupere las fuentes disponibles y muestre sus detalles.

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts(): recupera la lista de fuentes disponibles de la primera fuente de fuente en la lista actualizada.
-  fontInfo: una instancia de`PhysicalFontInfo` que contiene detalles sobre cada fuente.

## Conclusión

¡Felicidades! Ha recuperado con éxito una lista de fuentes disponibles utilizando Aspose.Words para .NET. Este tutorial lo ha guiado a través de cada paso, desde inicializar la configuración de fuente hasta mostrar los detalles de la fuente. Con este conocimiento, ahora puedes administrar las fuentes en tus documentos de Word con facilidad. Recuerde, Aspose.Words para .NET es una herramienta poderosa que puede mejorar significativamente sus capacidades de procesamiento de documentos. Entonces, continúe y explore más funciones para que su proceso de desarrollo sea aún más eficiente.

## Preguntas frecuentes

### ¿Puedo usar Aspose.Words para .NET con otros frameworks .NET?
Sí, Aspose.Words para .NET es compatible con varios marcos .NET, incluidos .NET Core y .NET 5+.

### ¿Cómo instalo Aspose.Words para .NET?
Puede instalarlo a través del Administrador de paquetes NuGet en Visual Studio buscando "Aspose.Words".

### ¿Es posible agregar varias carpetas de fuentes personalizadas?
 Sí, puede agregar varias carpetas de fuentes personalizadas creando varias`FolderFontSource` instancias y agregarlas a la lista de fuentes de fuentes.

### ¿Puedo recuperar detalles de fuentes de una fuente de fuente específica?
 Sí, puede recuperar detalles de fuente de cualquier fuente especificando el índice de la fuente en el`updatedFontSources` formación.

### ¿Aspose.Words para .NET admite la sustitución de fuentes?
Sí, admite la sustitución de fuentes para garantizar que el texto se represente correctamente incluso si la fuente original no está disponible.