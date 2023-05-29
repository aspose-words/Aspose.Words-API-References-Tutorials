---
title: Establecer carpeta de fuentes
linktitle: Establecer carpeta de fuentes
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a configurar el directorio de fuentes en Aspose.Words para .NET y asegure la disponibilidad de las fuentes utilizadas en sus documentos.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folder/
---
En este tutorial, le mostraremos cómo configurar el directorio de fuentes en Aspose.Words para .NET. Aprenderá a especificar el directorio que contiene las fuentes utilizadas en su documento de Word.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: Definir el directorio de documentos
Comience configurando la ruta del directorio a la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: establecer el directorio de fuentes
 Crear una instancia de la`FontSettings` clase y usa el`SetFontsFolder` método para especificar el directorio que contiene las fuentes. Reemplazar`"Fonts"` con el nombre del directorio de fuentes actual.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Paso 3: Cargue el documento con la configuración de fuente
 Utilizar el`LoadOptions` clase para especificar la configuración de fuente en el`FontSettings` opción. Luego usa el`Document` class para cargar el documento usando estas opciones.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Ejemplo de código fuente para Establecer carpeta de fuentes usando Aspose.Words para .NET 

```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusión
¡Felicidades! Ahora sabe cómo configurar el directorio de fuentes en Aspose.Words para .NET. Puede utilizar esta función para garantizar la disponibilidad de las fuentes utilizadas en su documento y para garantizar la coherencia en la visualización de las fuentes.
