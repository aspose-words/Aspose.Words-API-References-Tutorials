---
title: Habilitar Deshabilitar sustitución de fuentes
linktitle: Habilitar Deshabilitar sustitución de fuentes
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a habilitar o deshabilitar la sustitución de fuentes en documentos de Word usando Aspose.Words para .NET. Asegúrese de que sus documentos tengan un aspecto coherente en todas las plataformas.
type: docs
weight: 10
url: /es/net/working-with-fonts/enable-disable-font-substitution/
---
## Introducción

¿Alguna vez se encontró en una situación en la que las fuentes meticulosamente elegidas en un documento de Word se reemplazan cuando se ven en otra computadora? Molesto, ¿verdad? Esto sucede debido a la sustitución de fuentes, un proceso en el que el sistema reemplaza una fuente que falta por una disponible. ¡Pero no te preocupes! Con Aspose.Words para .NET, puede administrar y controlar fácilmente la sustitución de fuentes. En este tutorial, lo guiaremos a través de los pasos para habilitar o deshabilitar la sustitución de fuentes en sus documentos de Word, asegurando que sus documentos siempre luzcan tal como usted desea.

## Requisitos previos

Antes de profundizar en los pasos, asegurémonos de tener todo lo que necesita:

-  Aspose.Words para .NET: descargue la última versión[aquí](https://releases.aspose.com/words/net/).
- Visual Studio: cualquier versión que admita .NET.
- Conocimientos básicos de C#: esto le ayudará a seguir los ejemplos de codificación.

## Importar espacios de nombres

Para comenzar, asegúrese de tener importados los espacios de nombres necesarios en su proyecto. Agregue estos en la parte superior de su archivo C#:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Ahora, dividamos el proceso en pasos simples y manejables.

## Paso 1: configura tu proyecto

Primero, configure un nuevo proyecto en Visual Studio y agregue una referencia a la biblioteca Aspose.Words para .NET. Si aún no lo has hecho, descárgalo desde[Aspose sitio web](https://releases.aspose.com/words/net/).

## Paso 2: cargue su documento

A continuación, cargue el documento con el que desea trabajar. Así es como lo haces:

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos. Este código carga el documento en la memoria para que puedas manipularlo.

## Paso 3: configurar los ajustes de fuente

 Ahora, creemos un`FontSettings` Objeto para gestionar la configuración de sustitución de fuentes:

```csharp
FontSettings fontSettings = new FontSettings();
```

## Paso 4: establecer la sustitución de fuentes predeterminada

Establezca la sustitución de fuente predeterminada por una fuente de su elección. Esta fuente se utilizará si la fuente original no está disponible:

```csharp
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

En este ejemplo, usamos Arial como fuente predeterminada.

## Paso 5: deshabilite la sustitución de información de fuentes

Para deshabilitar la sustitución de información de fuentes, lo que impide que el sistema reemplace las fuentes faltantes con las disponibles, use el siguiente código:

```csharp
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
```

## Paso 6: aplicar la configuración de fuente al documento

Ahora, aplique estas configuraciones a su documento:

```csharp
doc.FontSettings = fontSettings;
```

## Paso 7: guarde su documento

Finalmente, guarde su documento modificado. Puedes guardarlo en cualquier formato que desees. Para este tutorial, lo guardaremos como PDF:

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```

## Conclusión

¡Y ahí lo tienes! Si sigue estos pasos, podrá controlar fácilmente la sustitución de fuentes en sus documentos de Word utilizando Aspose.Words para .NET. Esto garantiza que sus documentos mantengan la apariencia deseada, sin importar dónde se vean.

## Preguntas frecuentes

### ¿Puedo utilizar fuentes distintas a Arial para sustituirlas?

 ¡Absolutamente! Puede especificar cualquier fuente disponible en su sistema cambiando el nombre de la fuente en el`DefaultFontName` propiedad.

### ¿Qué sucede si la fuente predeterminada especificada no está disponible?

Si la fuente predeterminada no está disponible, Aspose.Words utilizará un mecanismo alternativo del sistema para encontrar un reemplazo adecuado.

### ¿Puedo habilitar la sustitución de fuentes nuevamente después de deshabilitarla?

 Sí, puedes alternar el`Enabled` propiedad de`FontInfoSubstitution` volver a`true` si desea habilitar la sustitución de fuentes nuevamente.

### ¿Hay alguna forma de comprobar qué fuentes se están sustituyendo?

Sí, Aspose.Words proporciona métodos para registrar y realizar un seguimiento de la sustitución de fuentes, lo que le permite ver qué fuentes se están reemplazando.

### ¿Puedo utilizar este método para otros formatos de documentos además de DOCX?

¡Definitivamente! Aspose.Words admite varios formatos y puede aplicar esta configuración de fuente a cualquier formato compatible.