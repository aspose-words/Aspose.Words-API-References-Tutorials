---
title: Habilitar Deshabilitar sustitución de fuentes
linktitle: Habilitar Deshabilitar sustitución de fuentes
second_title: API de procesamiento de documentos de Aspose.Words
description: En este tutorial, aprenda cómo habilitar o deshabilitar la sustitución de fuentes en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/enable-disable-font-substitution/
---
En este tutorial, lo guiaremos a través de cómo habilitar o deshabilitar la sustitución de fuentes en un documento de Word al procesarlo usando la biblioteca Aspose.Words para .NET. Habilitar o deshabilitar la sustitución de fuentes le permite controlar si las fuentes que faltan se reemplazan automáticamente con una fuente predeterminada. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#
- La biblioteca Aspose.Words para .NET instalada en su proyecto
- Un documento de Word que desea representar con o sin sustitución de fuente

## Paso 1: Definir el directorio de documentos
 Primero, debe establecer la ruta del directorio en la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta adecuada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento y configure los ajustes de fuente
 A continuación, cargaremos el documento de Word que desea representar y crearemos una instancia del`FontSettings` clase para manejar la configuración de la fuente. Estableceremos la anulación de la fuente predeterminada especificando el nombre de la fuente en`DefaultFontName` y deshabilite la anulación de información de fuente con`Enabled` ajustado a`false`.

```csharp
// Cargue el documento
Document doc = new Document(dataDir + "Rendering.docx");

// Configurar ajustes de fuente
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Aplicar la configuración de fuente al documento
doc.FontSettings = fontSettings;
```

## Paso 3: Guarde el documento renderizado
Finalmente, guardaremos el documento renderizado, que respetará la configuración de anulación de fuente definida.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Ejemplo de código fuente para Habilitar Deshabilitar sustitución de fuentes usando Aspose.Words para .NET 

```csharp

//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Conclusión
En este tutorial, vimos cómo habilitar o deshabilitar la sustitución de fuentes en un documento de Word al representarlo con Aspose.Words para .NET. Al controlar la sustitución de fuentes, puede influir en cómo se manejan las fuentes que faltan en sus documentos renderizados. No dudes en utilizar esta función para personalizar la gestión de fuentes en tus documentos de Word.

### Preguntas frecuentes

#### P: ¿Cómo puedo habilitar la sustitución de fuentes en un documento de Word con Aspose.Words?

R: Para habilitar la sustitución de fuentes en un documento de Word con Aspose.Words, puede usar la API para especificar las fuentes de sustitución que se usarán cuando las fuentes requeridas no estén disponibles. Esto asegurará una visualización de texto consistente, incluso sin las fuentes originales.

#### P: ¿Es posible deshabilitar la sustitución de fuentes en un documento de Word con Aspose.Words?

R: Sí, con Aspose.Words puede deshabilitar la sustitución de fuentes en un documento de Word. Mediante el uso de la API, puede evitar que Word sustituya las fuentes requeridas por otras fuentes, lo que mantiene la apariencia original del texto.

#### P: ¿Qué sucede cuando faltan las fuentes requeridas durante la sustitución en un documento de Word?

R: Cuando faltan las fuentes requeridas durante la sustitución en un documento de Word, Aspose.Words puede detectar este problema y brindarle opciones para solucionarlo. Puede optar por sustituir las fuentes que faltan por fuentes alternativas o incluir las fuentes que faltan en el documento, lo que garantiza una visualización correcta.

#### P: ¿Cómo puedo manejar las fuentes que faltan al sustituir un documento de Word con Aspose.Words?

R: Para manejar las fuentes que faltan al sustituir un documento de Word con Aspose.Words, puede usar la API para detectar las fuentes que faltan y proporcionar opciones de resolución. Puede optar por sustituir las fuentes que faltan por fuentes alternativas o incluir las fuentes que faltan en el documento, según sus necesidades.

#### P: ¿Es importante controlar la sustitución de fuentes en un documento de Word?

R: Sí, es importante controlar la sustitución de fuentes en un documento de Word para mantener la integridad visual del texto. Al usar Aspose.Words para habilitar o deshabilitar la sustitución de fuentes, puede asegurarse de que se utilicen las fuentes requeridas y evitar problemas con las fuentes faltantes o sustituidas.