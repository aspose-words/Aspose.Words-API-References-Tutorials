---
title: Establecer carpetas de fuentes del sistema y carpetas personalizadas
linktitle: Establecer carpetas de fuentes del sistema y carpetas personalizadas
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar carpetas de fuentes personalizadas y del sistema en documentos de Word usando Aspose.Words para .NET, garantizando así que sus documentos se muestren correctamente en diferentes entornos.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## Introducción

Imagina que estás creando un documento con un estilo de fuente único y descubres que las fuentes no se muestran correctamente en otra máquina. Es frustrante, ¿verdad? Aquí es donde entra en juego la configuración de carpetas de fuentes. Con Aspose.Words para .NET, puedes definir carpetas de fuentes personalizadas y del sistema para garantizar que tus documentos siempre tengan el aspecto deseado. Veamos cómo puedes lograrlo.

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:

-  Biblioteca Aspose.Words para .NET: si aún no lo ha hecho, descárguela[aquí](https://releases.aspose.com/words/net/).
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

Ahora, vamos a dividir el proceso en pasos simples.

## Paso 1: Cargue el documento

 Para comenzar, cargue su documento de Word en Aspose.Words`Document` objeto. Este documento será en el que deseamos configurar las carpetas de fuentes.

```csharp
// Ruta al directorio de su documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 2: Inicializar la configuración de fuentes

 Crear una nueva instancia de`FontSettings`Este objeto le permitirá administrar fuentes de fuentes.

```csharp
FontSettings fontSettings = new FontSettings();
```

## Paso 3: Recuperar fuentes del sistema

Recupere las fuentes de fuentes predeterminadas del sistema. En una máquina Windows, esto normalmente incluye "Windows\Fonts\" directorio.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## Paso 4: Agregar una carpeta de fuentes personalizada

Agregue una carpeta personalizada que contenga sus fuentes adicionales. Esto resulta útil si tiene fuentes específicas que no están instaladas en el directorio de fuentes del sistema.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## Paso 5: Actualizar las fuentes

 Convierte la lista de fuentes de fuentes nuevamente en una matriz y configúrala en`FontSettings` objeto.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Paso 6: Aplicar la configuración de fuentes al documento

 Por último, aplique la configuración`FontSettings` a su documento y guárdelo en el formato deseado, como PDF.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusión

¡Y ya está! Si sigue estos pasos, podrá asegurarse de que sus documentos de Word utilicen las fuentes correctas, ya sean fuentes del sistema o fuentes personalizadas almacenadas en un directorio específico. Esta configuración ayuda a mantener la integridad de la apariencia de su documento en diferentes entornos.

## Preguntas frecuentes

### ¿Qué sucede si falta una fuente en las carpetas del sistema y personalizadas?

Aspose.Words utilizará una fuente predeterminada para sustituir la fuente faltante, garantizando que el documento siga siendo legible.

### ¿Puedo agregar varias carpetas de fuentes personalizadas?

 Sí, puedes agregar varias carpetas de fuentes personalizadas repitiendo el proceso de creación.`FolderFontSource` objetos y agregarlos a la lista de fuentes.

### ¿Es posible utilizar rutas de red para carpetas de fuentes personalizadas?

 Sí, puede especificar una ruta de red en el`FolderFontSource` constructor.

### ¿Qué formatos de archivos admite Aspose.Words para guardar documentos?

Aspose.Words admite varios formatos, incluidos DOCX, PDF, HTML y más.

### ¿Cómo manejo las notificaciones de sustitución de fuentes?

 Puede gestionar las notificaciones de sustitución de fuentes mediante el uso de`FontSettings` de la clase`FontSubstitutionWarning`evento.