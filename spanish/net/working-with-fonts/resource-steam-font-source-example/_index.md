---
title: Ejemplo de fuente de fuente Steam de recursos
linktitle: Ejemplo de fuente de fuente Steam de recursos
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar el origen de fuentes de flujo de recursos para cargar fuentes personalizadas en Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/resource-steam-font-source-example/
---

En este tutorial, lo guiaremos a través de cómo usar Fuente de fuentes de flujo de recursos con Aspose.Words para .NET. Esta fuente de fuentes le permite cargar fuentes desde un flujo de recursos, lo que puede ser útil cuando desea incorporar fuentes personalizadas en su aplicación.

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

## Paso 2: Cargue el documento y establezca la fuente de fuente del flujo de recursos
 A continuación, cargaremos el documento usando el`Document` class y configure la fuente de fuente de flujo de recursos usando el`FontSettings.DefaultInstance.SetFontsSources()` clase. Esto permitirá que Aspose.Words encuentre las fuentes en el flujo de recursos.

```csharp
// Cargue el documento y establezca la fuente de fuente del flujo de recursos
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## Paso 3: Guarde el documento
Finalmente, guardaremos el documento. Las fuentes se cargarán desde el flujo de recursos especificado y se incrustarán en el documento.

```csharp
// Guardar el documento
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Ejemplo de código fuente para Resource Steam Font Source Example usando Aspose.Words para .NET 

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Conclusión
En este tutorial, aprendió a usar el origen de fuente de flujo de recursos con Aspose.Words para .NET. Esta característica le permite cargar fuentes desde una fuente de recursos, lo cual es útil cuando desea incrustar fuentes personalizadas en sus documentos. Experimente con diferentes fuentes y explore las posibilidades que ofrece Aspose.Words para la gestión de fuentes.
