---
title: Establecer carpeta de fuentes
linktitle: Establecer carpeta de fuentes
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo configurar el directorio de fuentes en Aspose.Words para .NET y garantice la disponibilidad de las fuentes utilizadas en sus documentos.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folder/
---
En este tutorial, le mostraremos cómo configurar el directorio de fuentes en Aspose.Words para .NET. Aprenderá cómo especificar el directorio que contiene las fuentes utilizadas en su documento de Word.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#.
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: definir el directorio de documentos
 Comience configurando la ruta del directorio a la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta apropiada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: configurar el directorio de fuentes
 Crear una instancia del`FontSettings` clase y utilizar el`SetFontsFolder` método para especificar el directorio que contiene las fuentes. Reemplazar`"Fonts"` con el nombre del directorio de fuentes real.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Paso 3: cargue el documento con la configuración de fuente
 Utilizar el`LoadOptions` clase para especificar la configuración de fuente en el`FontSettings` opción. Luego usa el`Document` clase para cargar el documento usando estas opciones.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Código fuente de muestra para Establecer carpeta de fuentes usando Aspose.Words para .NET 

```csharp

//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusión
¡Enhorabuena! Ahora sabe cómo configurar el directorio de fuentes en Aspose.Words para .NET. Puede utilizar esta función para garantizar la disponibilidad de las fuentes utilizadas en su documento y garantizar la coherencia en la visualización de las fuentes.

### Preguntas frecuentes

#### P: ¿Cómo puedo configurar una carpeta de fuentes personalizadas en Aspose.Words?

 R: Para configurar una carpeta de fuentes personalizadas en Aspose.Words, puede usar el`FontsFolder` clase y el`SetFontsFolders` método que especifica la ruta a la carpeta que contiene sus fuentes.

#### P: ¿Puedo configurar varias carpetas de fuentes en Aspose.Words?

 R: Sí, puede configurar varias carpetas de fuentes en Aspose.Words llamando al`SetFontsFolders` método varias veces con las rutas de las diferentes carpetas de fuentes que desea utilizar.

#### P: ¿Qué sucede si una fuente utilizada en el documento no está presente en las carpetas de fuentes definidas?

R: Si una fuente utilizada en el documento no está presente en las carpetas de fuentes definidas en Aspose.Words, se utilizará una fuente sustituta. Esto garantiza que el texto del documento siempre se mostrará correctamente, incluso si la fuente original no está disponible.

#### P: ¿Las carpetas de fuentes definidas en Aspose.Words tienen prioridad sobre las fuentes instaladas en el sistema?

R: Sí, las carpetas de fuentes definidas en Aspose.Words tienen prioridad sobre las fuentes instaladas en el sistema. Esto significa que si una fuente con el mismo nombre está presente tanto en las carpetas de fuentes definidas como en las fuentes del sistema, la versión en la carpeta de fuentes se utilizará al procesar documentos de Word.