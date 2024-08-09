---
title: Establecer carpetas de fuentes con prioridad
linktitle: Establecer carpetas de fuentes con prioridad
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar carpetas de fuentes con prioridad en documentos de Word usando Aspose.Words para .NET. Nuestra guía garantiza que sus documentos se reproduzcan perfectamente en todo momento.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-with-priority/
---
## Introducción

En el mundo de la manipulación de documentos, configurar carpetas de fuentes personalizadas puede marcar una gran diferencia a la hora de garantizar que sus documentos se reproduzcan perfectamente, sin importar dónde se vean. Hoy, profundizaremos en cómo puede configurar carpetas de fuentes con prioridad en sus documentos de Word usando Aspose.Words para .NET. Esta guía completa lo guiará en cada paso, haciendo que el proceso sea lo más sencillo posible.

## Requisitos previos

Antes de comenzar, asegurémonos de tener todo lo que necesitamos. Aquí hay una lista de verificación rápida:

-  Aspose.Words para .NET: Es necesario tener instalada esta biblioteca. Si aún no lo tienes, puedes[descárgalo aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: asegúrese de tener un entorno de desarrollo .NET que funcione, como Visual Studio.
-  Directorio de documentos: asegúrese de tener un directorio para sus documentos. Para nuestros ejemplos, usaremos`"YOUR DOCUMENT DIRECTORY"` como marcador de posición para esta ruta.

## Importar espacios de nombres

Lo primero es lo primero, necesitamos importar los espacios de nombres necesarios. Estos espacios de nombres son esenciales para acceder a las clases y métodos proporcionados por Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Ahora, analicemos cada paso para configurar las carpetas de fuentes con prioridad.

## Paso 1: configura tus fuentes de fuentes

Para comenzar, querrás definir las fuentes de fuente. Aquí es donde le dices a Aspose.Words dónde buscar fuentes. Puede especificar varias carpetas de fuentes e incluso establecer su prioridad.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
    new SystemFontSource(), 
    new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

En este ejemplo, configuramos dos fuentes de fuente:
- SystemFontSource: esta es la fuente de fuente predeterminada que incluye todas las fuentes instaladas en su sistema.
-  FolderFontSource: esta es una carpeta de fuentes personalizadas ubicada en`C:\\MyFonts\\` . El`true` El parámetro especifica que esta carpeta debe escanearse de forma recursiva y`1` establece su prioridad.

## Paso 2: cargue su documento

A continuación, cargue el documento con el que desea trabajar. Asegúrese de que el documento esté ubicado en el directorio especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Esta línea de código carga un documento llamado`Rendering.docx` desde su directorio de documentos.

## Paso 3: guarde su documento con la nueva configuración de fuente

Finalmente, guarde su documento. Cuando guarde el documento, Aspose.Words utilizará la configuración de fuente que especificó.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

 Esto guarda el documento como PDF en su directorio de documentos con el nombre`WorkingWithFonts.SetFontsFoldersWithPriority.pdf`.

## Conclusión

¡Y ahí lo tienes! Ha configurado correctamente carpetas de fuentes con prioridad utilizando Aspose.Words para .NET. Al especificar prioridades y carpetas de fuentes personalizadas, puede garantizar que sus documentos se reproduzcan de manera consistente, independientemente de dónde se vean. Esto es especialmente útil en entornos donde fuentes específicas no están instaladas de forma predeterminada.

## Preguntas frecuentes

### ¿Por qué necesitaría configurar carpetas de fuentes personalizadas?
La configuración de carpetas de fuentes personalizadas garantiza que sus documentos se representen correctamente, incluso si utilizan fuentes que no están instaladas en el sistema donde se están viendo.

### ¿Puedo configurar varias carpetas de fuentes personalizadas?
Sí, puede especificar varias carpetas de fuentes. Aspose.Words le permite establecer la prioridad para cada carpeta, asegurando que las fuentes más importantes se encuentren primero.

### ¿Qué sucede si falta una fuente en todas las fuentes especificadas?
Si falta una fuente en todas las fuentes especificadas, Aspose.Words utilizará una fuente alternativa para garantizar que el documento aún sea legible.

### ¿Puedo cambiar la prioridad de las fuentes del sistema?
Las fuentes del sistema siempre se incluyen de forma predeterminada, pero puede establecer su prioridad en relación con sus carpetas de fuentes personalizadas.

### ¿Es posible utilizar rutas de red para carpetas de fuentes personalizadas?
Sí, puede especificar rutas de red como carpetas de fuentes personalizadas, lo que le permite centralizar los recursos de fuentes en una ubicación de red.