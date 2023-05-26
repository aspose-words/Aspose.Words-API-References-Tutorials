---
title: Configuración de fuentes Instancia predeterminada
linktitle: Configuración de fuentes Instancia predeterminada
second_title: Referencia de API de Aspose.Words para .NET
description: En este tutorial, aprenda a configurar los ajustes de fuente predeterminados en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/font-settings-default-instance/
---

En este tutorial, lo guiaremos a través de cómo configurar las configuraciones de fuentes predeterminadas en un documento de Word utilizando la biblioteca Aspose.Words para .NET. La configuración de fuente predeterminada le permite especificar las fuentes de fuente utilizadas al cargar y renderizar documentos. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

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

## Paso 2: configure los ajustes de fuente predeterminados
 A continuación, crearemos una instancia de`FontSettings` usando`FontSettings.DefaultInstance`y luego especificaremos las fuentes de fuentes utilizadas al cargar y renderizar documentos. En este ejemplo, estamos usando una fuente de fuente del sistema y una fuente de fuente de carpeta.

```csharp
// Configurar los ajustes de fuente predeterminados
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Paso 3: Cargue el documento con la configuración de fuente
 Ahora cargaremos el documento usando`LoadOptions` y especificando la configuración de fuente a utilizar.

```csharp
// Cargue el documento con la configuración de fuente
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Ejemplo de código fuente para la instancia predeterminada de configuración de fuente usando Aspose.Words para .NET 
```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusión
En este tutorial, vimos cómo configurar los ajustes de fuente predeterminados en un documento de Word con Aspose.Words para .NET. Al especificar las fuentes de fuentes utilizadas al cargar y renderizar documentos, puede controlar la apariencia de las fuentes en sus documentos. Siéntase libre de usar esta función para personalizar la configuración de fuentes en sus proyectos.