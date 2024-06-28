---
title: Establecer la configuración de reserva de fuentes
linktitle: Establecer la configuración de reserva de fuentes
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar la configuración de reserva de fuentes en Aspose.Words para .NET. Esta guía completa garantiza que todos los caracteres de sus documentos se muestren correctamente.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-font-fallback-settings/
---

Cuando se trabaja con documentos que contienen diversos elementos de texto, como diferentes idiomas o caracteres especiales, es fundamental asegurarse de que estos elementos se muestren correctamente. Aspose.Words para .NET ofrece una característica poderosa llamada Configuración de reserva de fuentes, que ayuda a definir reglas para sustituir fuentes cuando la fuente original no admite ciertos caracteres. En esta guía, exploraremos cómo configurar la configuración de reserva de fuentes usando Aspose.Words para .NET en un tutorial paso a paso.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

- Conocimientos básicos de C#: familiaridad con el lenguaje de programación C# y el marco .NET.
-  Aspose.Words para .NET: descargue e instale desde[enlace de descarga](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: una configuración como Visual Studio para escribir y ejecutar su código.
-  Documento de muestra: tenga un documento de muestra (p. ej.,`Rendering.docx`) listo para la prueba.
- XML de reglas de reserva de fuentes: prepare un archivo XML que defina las reglas de reserva de fuentes.

## Importar espacios de nombres

Para utilizar Aspose.Words, debe importar los espacios de nombres necesarios. Esto permite el acceso a varias clases y métodos necesarios para el procesamiento de documentos.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Paso 1: definir el directorio de documentos

Primero, defina el directorio donde está almacenado su documento. Esto es esencial para localizar y procesar su documento.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargue el documento

 Cargue su documento en Aspose.Words`Document` objeto. Este paso le permite trabajar con el documento mediante programación.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: configurar los ajustes de fuente

 Crear un nuevo`FontSettings` objeto y cargue la configuración de reserva de fuente desde un archivo XML. Este archivo XML contiene las reglas para la reserva de fuentes.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Paso 4: aplicar la configuración de fuente al documento

 Asigne el configurado`FontSettings`al documento. Esto garantiza que se apliquen las reglas de reserva de fuentes al renderizar el documento.

```csharp
doc.FontSettings = fontSettings;
```

## Paso 5: guarde el documento

Finalmente, guarde el documento. La configuración de reserva de fuente se utilizará durante la operación de guardar para garantizar una sustitución de fuente adecuada.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Archivo XML: reglas de reserva de fuentes

A continuación se muestra un ejemplo de cómo debería verse su archivo XML que define las reglas de reserva de fuentes:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Conclusión

Si sigue estos pasos, podrá configurar y utilizar eficazmente la configuración de reserva de fuentes en Aspose.Words para .NET. Esto garantiza que sus documentos muestren todos los caracteres correctamente, incluso si la fuente original no admite ciertos caracteres. La implementación de estas configuraciones mejorará enormemente la calidad y legibilidad de sus documentos.

## Preguntas frecuentes

### P1: ¿Qué es la reserva de fuentes?

Font Fallback es una función que permite la sustitución de fuentes cuando la fuente original no admite ciertos caracteres, lo que garantiza una visualización adecuada de todos los elementos del texto.

### P2: ¿Puedo especificar varias fuentes alternativas?

Sí, puede especificar varias fuentes alternativas en las reglas XML. Aspose.Words verificará cada fuente en el orden especificado hasta que encuentre una que admita el carácter.

### P3: ¿Dónde puedo descargar Aspose.Words para .NET?

 Puedes descargarlo desde el[Página de descarga de Aspose](https://releases.aspose.com/words/net/).

### P4: ¿Cómo creo el archivo XML para las reglas de reserva de fuentes?

El archivo XML se puede crear utilizando cualquier editor de texto. Debe seguir la estructura que se muestra en el ejemplo proporcionado en este tutorial.

### P5: ¿Hay soporte disponible para Aspose.Words?

 Sí, puedes encontrar soporte en el[Foro de soporte de Aspose.Words](https://forum.aspose.com/c/words/8).