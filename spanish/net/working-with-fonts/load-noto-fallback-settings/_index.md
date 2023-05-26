---
title: Cargar la configuración de respaldo de Noto
linktitle: Cargar la configuración de respaldo de Noto
second_title: Referencia de API de Aspose.Words para .NET
description: En este tutorial, aprenda a cargar parámetros de anulación de Noto en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/load-noto-fallback-settings/
---
En este tutorial, lo guiaremos a través de cómo cargar la configuración de sustitución de fuentes Noto en un documento de Word utilizando la biblioteca Aspose.Words para .NET. La configuración de sustitución de fuentes de Noto le permite gestionar la sustitución de fuentes al mostrar o imprimir documentos. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

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

## Paso 2: Cargue el documento y configure los ajustes de sustitución de fuentes
 A continuación, cargaremos el documento usando el`Document` clase y configure los ajustes de anulación de fuente usando el`FontSettings` clase. Cargaremos la configuración de respaldo de la fuente Noto usando el`LoadNotoFallbackSettings()` método.

```csharp
// Cargue el documento y configure los ajustes de sustitución de fuentes
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
```

## Paso 3: Guarde el documento
Finalmente, guardaremos el documento con la configuración de sustitución de fuentes Noto aplicada.

```csharp
// Guardar el documento
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");
```


### Ejemplo de código fuente para la configuración de respaldo de Noto usando Aspose.Words para .NET 
```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");

```

## Conclusión
En este tutorial, vimos cómo cargar la configuración de sustitución de fuentes Noto en un documento de Word con Aspose.Words para .NET. La configuración de sustitución de fuentes de Noto le permite administrar la sustitución de fuentes para mejorar la visualización e impresión de sus documentos. No dude en utilizar esta función para personalizar la sustitución de fuentes según sus necesidades.