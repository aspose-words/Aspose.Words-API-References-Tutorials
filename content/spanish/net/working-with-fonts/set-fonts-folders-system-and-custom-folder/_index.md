---
title: Establecer sistema de carpetas de fuentes y carpeta personalizada
linktitle: Establecer sistema de carpetas de fuentes y carpeta personalizada
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar carpetas de fuentes personalizadas y del sistema en documentos de Word utilizando Aspose.Words para .NET, garantizando que sus documentos se muestren correctamente en diferentes entornos.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## Introducción

Imagine que está creando un documento con un estilo de fuente único, sólo para descubrir que las fuentes no se muestran correctamente en otra máquina. Frustrante, ¿verdad? Aquí es donde entra en juego la configuración de carpetas de fuentes. Con Aspose.Words para .NET, puede definir carpetas de fuentes personalizadas y del sistema para garantizar que sus documentos siempre tengan el aspecto previsto. Profundicemos en cómo puede lograr esto.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

-  Aspose.Words para la biblioteca .NET: si aún no lo ha hecho, descárguelo[aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: un IDE como Visual Studio.
- Conocimientos básicos de C#: la familiaridad con C# le ayudará a seguir los ejemplos de código.

## Importar espacios de nombres

Primero, importe los espacios de nombres necesarios en su proyecto:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Ahora, dividamos el proceso en pasos simples.

## Paso 1: cargue el documento

 Para comenzar, cargue su documento de Word en Aspose.Words`Document` objeto. Este documento será aquel en el que desea configurar las carpetas de fuentes.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 2: inicializar la configuración de fuente

 Crear una nueva instancia de`FontSettings`. Este objeto le permitirá administrar las fuentes de fuentes.

```csharp
FontSettings fontSettings = new FontSettings();
```

## Paso 3: recuperar las fuentes de fuentes del sistema

Recupere las fuentes de fuentes predeterminadas del sistema. En una máquina con Windows, esto normalmente incluye el archivo "Windows\Fonts\"directorio.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## Paso 4: agregue una carpeta de fuentes personalizadas

Agregue una carpeta personalizada que contenga sus fuentes adicionales. Esto es útil si tiene fuentes específicas que no están instaladas en el directorio de fuentes del sistema.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## Paso 5: actualice las fuentes de fuentes

 Convierta la lista de fuentes de fuentes nuevamente a una matriz y configúrela en el`FontSettings` objeto.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Paso 6: aplicar la configuración de fuente al documento

 Finalmente, aplique lo configurado.`FontSettings` a su documento y guárdelo en el formato deseado, como PDF.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusión

¡Y ahí lo tienes! Si sigue estos pasos, puede asegurarse de que sus documentos de Word utilicen las fuentes correctas, ya sean fuentes del sistema o personalizadas almacenadas en un directorio específico. Esta configuración ayuda a mantener la integridad de la apariencia de su documento en diferentes entornos.

## Preguntas frecuentes

### ¿Qué sucede si falta una fuente tanto en las carpetas del sistema como en las personalizadas?

Aspose.Words utilizará una fuente predeterminada para sustituir la fuente que falta, asegurando que el documento siga siendo legible.

### ¿Puedo agregar varias carpetas de fuentes personalizadas?

 Sí, puede agregar varias carpetas de fuentes personalizadas repitiendo el proceso de creación.`FolderFontSource` objetos y agregarlos a la lista de fuentes de fuentes.

### ¿Es posible utilizar rutas de red para carpetas de fuentes personalizadas?

 Sí, puede especificar una ruta de red en el`FolderFontSource` constructor.

### ¿Qué formatos de archivo admite Aspose.Words para guardar documentos?

Aspose.Words admite varios formatos, incluidos DOCX, PDF, HTML y más.

### ¿Cómo manejo las notificaciones de sustitución de fuentes?

 Puede manejar las notificaciones de sustitución de fuentes utilizando el`FontSettings` clase`FontSubstitutionWarning`evento.