---
title: Establecer instancia predeterminada de carpetas de fuentes
linktitle: Establecer instancia predeterminada de carpetas de fuentes
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo configurar carpetas de fuentes para la instancia predeterminada en Aspose.Words para .NET con este tutorial paso a paso. Personaliza tus documentos de Word sin esfuerzo.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-default-instance/
---
## Introducción

¡Hola, compañero codificador! Si está trabajando con documentos de Word en .NET, probablemente conozca la importancia de tener las fuentes correctas. Hoy, profundizaremos en cómo configurar carpetas de fuentes para la instancia predeterminada usando Aspose.Words para .NET. Imagine tener todas sus fuentes personalizadas al alcance de su mano, haciendo que sus documentos se vean exactamente como los imagina. Suena genial, ¿verdad? ¡Empecemos!

## Requisitos previos

Antes de profundizar en los detalles esenciales, asegurémonos de que tiene todo lo que necesita:
-  Aspose.Words para .NET: asegúrese de tener la biblioteca instalada. Si no, puedes[descárgalo aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: Visual Studio o cualquier otro IDE compatible con .NET.
- Conocimientos básicos de C#: debe sentirse cómodo con la programación en C#.
- Carpeta de fuentes: un directorio que contiene sus fuentes personalizadas.

## Importar espacios de nombres

Primero lo primero, importemos los espacios de nombres necesarios. Esto ayuda a acceder a las clases y métodos necesarios para configurar la carpeta de fuentes.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Dividamos el proceso en pasos simples y digeribles.

## Paso 1: definir el directorio de datos

Todo gran viaje comienza con un solo paso, y el nuestro comienza con la definición del directorio donde se almacena su documento. Aquí es donde Aspose.Words buscará su documento de Word.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Aquí, reemplace`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos. Aquí es donde se encuentra su documento fuente y donde se guardará el resultado.

## Paso 2: configurar la carpeta de fuentes

 Ahora, digamos a Aspose.Words dónde encontrar sus fuentes personalizadas. Esto se hace configurando la carpeta de fuentes usando el`FontSettings.DefaultInstance.SetFontsFolder` método.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

 En esta línea,`"C:\\MyFonts\\"` es la ruta a su carpeta de fuentes personalizadas. El segundo parámetro,`true`, indica que las fuentes de esta carpeta deben escanearse de forma recursiva.

## Paso 3: cargue su documento

 Con la carpeta de fuentes configurada, el siguiente paso es cargar su documento de Word en Aspose.Words. Esto se hace usando el`Document` clase.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Aquí,`dataDir + "Rendering.docx"` se refiere a la ruta completa de su documento de Word. Asegúrese de que su documento esté en el directorio especificado.

## Paso 4: guarde el documento

El último paso es guardar su documento después de configurar la carpeta de fuentes. Esto garantiza que sus fuentes personalizadas se apliquen correctamente en la salida.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

Esta línea guarda su documento como PDF con las fuentes personalizadas aplicadas. El archivo de salida se ubicará en el mismo directorio que su documento fuente.

## Conclusión

¡Y ahí lo tienes! Configurar carpetas de fuentes para la instancia predeterminada en Aspose.Words para .NET es muy sencillo si lo divides en pasos simples. Si sigue esta guía, puede asegurarse de que sus documentos de Word se vean exactamente como los desea, con todas sus fuentes personalizadas en su lugar. ¡Así que adelante, pruébalo y haz que tus documentos brillen!

## Preguntas frecuentes

### ¿Puedo configurar varias carpetas de fuentes?
 Sí, puede configurar varias carpetas de fuentes utilizando el`SetFontsFolders` método que acepta una variedad de rutas de carpetas.

### ¿Qué formatos de archivo admite Aspose.Words para guardar documentos?
Aspose.Words admite varios formatos, incluidos DOCX, PDF, HTML, EPUB y más.

### ¿Es posible utilizar fuentes en línea en Aspose.Words?
No, Aspose.Words actualmente solo admite archivos de fuentes locales.

### ¿Cómo puedo asegurarme de que mis fuentes personalizadas estén integradas en el PDF guardado?
 Al configurar el`FontSettings` correctamente y asegurándose de que las fuentes estén disponibles, Aspose.Words las incrustará en la salida PDF.

### ¿Qué sucede si no se encuentra una fuente en la carpeta especificada?
Aspose.Words utilizará una fuente alternativa si no se encuentra la fuente especificada.