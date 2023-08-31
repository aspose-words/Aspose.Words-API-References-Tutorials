---
title: Cargar la configuración alternativa de Noto
linktitle: Cargar la configuración alternativa de Noto
second_title: API de procesamiento de documentos Aspose.Words
description: En este tutorial, aprenderá cómo cargar parámetros de anulación de Noto en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/load-noto-fallback-settings/
---
En este tutorial, le explicaremos cómo cargar la configuración de sustitución de fuentes Noto en un documento de Word utilizando la biblioteca Aspose.Words para .NET. La configuración de sustitución de fuentes de Noto le permite administrar la sustitución de fuentes al mostrar o imprimir documentos. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#.
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: definir el directorio de documentos
 Primero, debe configurar la ruta del directorio a la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta apropiada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: cargue el documento y configure los ajustes de sustitución de fuentes
 A continuación, cargaremos el documento usando el`Document` clase y configurar los ajustes de anulación de fuente utilizando el`FontSettings` clase. Cargaremos la configuración alternativa de fuente Noto usando el`LoadNotoFallbackSettings()` método.

```csharp
// Cargue el documento y configure los ajustes de sustitución de fuentes
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
```

## Paso 3: guarde el documento
Finalmente, guardaremos el documento con la configuración de sustitución de fuentes Noto aplicada.

```csharp
// guardar el documento
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");
```


### Código fuente de muestra para la configuración alternativa de Noto usando Aspose.Words para .NET 
```csharp

//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");

```

## Conclusión
En este tutorial, vimos cómo cargar la configuración de sustitución de fuentes Noto en un documento de Word con Aspose.Words para .NET. La configuración de sustitución de fuentes de Noto le permite administrar la sustitución de fuentes para mejorar la visualización y la impresión de sus documentos. No dude en utilizar esta función para personalizar la sustitución de fuentes según sus necesidades.

### Preguntas frecuentes

#### P: ¿Cómo puedo cargar la configuración de sustitución de fuentes Noto en un documento de Word con Aspose.Words?

R: Para cargar la configuración de sustitución de fuentes Noto en un documento de Word con Aspose.Words, primero debe descargar las fuentes Noto de la fuente oficial. Luego puede usar la API Aspose.Words para cargar esas fuentes en el documento y configurarlas para su sustitución cuando sea necesario.

#### P: ¿El uso de fuentes Noto para la sustitución en documentos de Word garantiza una visualización de texto coherente?

R: Sí, el uso de fuentes Noto para sustitución en documentos de Word garantiza una visualización de texto consistente. Las fuentes Noto están diseñadas para admitir muchos idiomas y caracteres, lo que ayuda a mantener una apariencia uniforme incluso cuando las fuentes requeridas no están disponibles.

#### P: ¿Las fuentes Noto son gratuitas?

R: Sí, las fuentes Noto son gratuitas y de código abierto. Se pueden descargar y utilizar en tus proyectos sin coste alguno. Esto lo convierte en una excelente opción para mejorar la visualización de fuentes en sus documentos de Word sin tener que invertir en fuentes comerciales.

#### P: ¿El uso de fuentes Noto hace que mis documentos de Word sean más accesibles?

R: Sí, el uso de fuentes Noto para sustitución en documentos de Word ayuda a que sus documentos sean más accesibles. Las fuentes Noto admiten muchos idiomas y caracteres, lo que garantiza una mejor legibilidad y comprensión para los usuarios que ven sus documentos en diferentes idiomas.