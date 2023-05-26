---
title: Establecer la configuración de reserva de fuentes
linktitle: Establecer la configuración de reserva de fuentes
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a establecer la configuración de sustitución de fuentes en Aspose.Words para .NET y personalizar la sustitución de fuentes en sus documentos de Word.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-font-fallback-settings/
---
En este tutorial, le mostraremos cómo establecer la configuración de sustitución de fuentes en un documento de Word utilizando Aspose.Words para .NET. La configuración de sustitución de fuentes le permite especificar fuentes de reemplazo para usar cuando las fuentes especificadas no están disponibles.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: Definir el directorio de documentos
Comience configurando la ruta del directorio a la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue la configuración de sustitución de fuentes
 Crear una instancia de la`FontSettings` clase y usa el`Load`método para cargar la configuración de sustitución de fuentes desde un archivo XML. El archivo XML especificado debe contener las reglas de sustitución de fuentes que se utilizarán.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## Paso 3: Aplicar la configuración de sustitución de fuentes
 Asocie la configuración de sustitución de fuentes con el documento asignándolas a la configuración del documento.`FontSettings` propiedad.

```csharp
doc.FontSettings = fontSettings;
```

## Paso 4: Guarde el documento
 Guarde el documento usando el`Save` metodo de la`Document` con la ruta y el nombre de archivo adecuados.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### Ejemplo de código fuente para establecer la configuración de reserva de fuentes mediante Aspose.Words para .NET 
```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Conclusión
En este tutorial, aprendió cómo establecer la configuración de sustitución de fuentes en un documento de Word usando Aspose.Words para .NET. Experimente con diferentes reglas de sustitución de fuentes para asegurarse de que su documento se vea consistente, incluso cuando las fuentes especificadas no estén disponibles.
