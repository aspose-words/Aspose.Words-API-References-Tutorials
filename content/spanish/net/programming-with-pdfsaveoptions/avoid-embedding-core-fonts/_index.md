---
title: Reduzca el tamaño del archivo PDF al no incrustar fuentes principales
linktitle: Reduzca el tamaño del archivo PDF al no incrustar fuentes principales
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo reducir el tamaño del archivo PDF al no incorporar fuentes principales usando Aspose.Words para .NET. Siga nuestra guía paso a paso para optimizar sus archivos PDF.
type: docs
weight: 10
url: /es/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---
## Introducción

¿Alguna vez te has rascado la cabeza preguntándote por qué tus archivos PDF son tan grandes? Bueno, no estás solo. Un culpable común es la incorporación de fuentes básicas como Arial y Times New Roman. Afortunadamente, Aspose.Words para .NET tiene una manera ingeniosa de abordar este problema. En este tutorial, le mostraré cómo reducir el tamaño de su archivo PDF evitando la incrustación de estas fuentes principales. ¡Vamos a sumergirnos de lleno!

## Requisitos previos

Antes de embarcarnos en este emocionante viaje, asegurémonos de que tiene todo lo que necesita. Aquí hay una lista de verificación rápida:

-  Aspose.Words para .NET: asegúrese de tener instalado Aspose.Words para .NET. Si aún no lo tienes, puedes descargarlo.[aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: necesitará un entorno de desarrollo como Visual Studio.
- Un documento de Word: usaremos un documento de Word (por ejemplo, "Rendering.docx") para este tutorial.
- Conocimientos básicos de C#: una comprensión básica de C# le ayudará a seguir adelante.

Muy bien, ahora que estamos listos, ¡entremos en el meollo de la cuestión!

## Importar espacios de nombres

Primero lo primero, importemos los espacios de nombres necesarios. Este paso garantiza que tengamos acceso a todas las funcionalidades de Aspose.Words que necesitamos.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Paso 1: Inicialice su directorio de documentos

Antes de comenzar a manipular nuestro documento, debemos especificar el directorio donde están almacenados nuestros documentos. Esto es esencial para acceder a los archivos.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real donde se encuentra su documento de Word.

## Paso 2: cargue el documento de Word

A continuación, debemos cargar el documento de Word que queremos convertir a PDF. En este ejemplo, utilizamos un documento llamado "Rendering.docx".

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Esta línea de código carga el documento en la memoria, listo para su posterior procesamiento.

## Paso 3: configurar las opciones de guardar PDF

¡Ahora viene la parte mágica! Configuraremos las opciones de guardado de PDF para evitar incrustar fuentes principales. Este es el paso clave que ayuda a reducir el tamaño del archivo PDF.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    UseCoreFonts = true
};
```

 Configuración`UseCoreFonts` a`true` garantiza que las fuentes principales como Arial y Times New Roman no estén incrustadas en el PDF, lo que reduce significativamente el tamaño del archivo.

## Paso 4: guarde el documento como PDF

Finalmente guardamos el documento de Word como PDF usando las opciones de guardado configuradas. Este paso genera el archivo PDF sin incrustar las fuentes principales.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

¡Y ahí lo tienes! Su archivo PDF ahora se guarda en el directorio especificado sin esas voluminosas fuentes principales.

## Conclusión

Reducir el tamaño del archivo PDF puede ser muy sencillo con Aspose.Words para .NET. Al evitar la incrustación de fuentes principales, puede reducir significativamente el tamaño del archivo, lo que facilita compartir y almacenar sus documentos. Espero que este tutorial haya sido útil y le haya dado una comprensión clara del proceso. Recuerde, ¡pequeños ajustes pueden marcar una gran diferencia!

## Preguntas frecuentes

### ¿Por qué debería evitar incrustar fuentes principales en archivos PDF?
Evitar incrustar fuentes principales reduce el tamaño del archivo, lo que facilita compartirlo y almacenarlo.

### ¿Puedo seguir viendo el PDF correctamente sin las fuentes principales integradas?
Sí, las fuentes principales como Arial y Times New Roman generalmente están disponibles en la mayoría de los sistemas.

### ¿Qué pasa si necesito incrustar fuentes personalizadas?
 Puedes personalizar el`PdfSaveOptions`para incrustar fuentes específicas según sea necesario.

### ¿Aspose.Words para .NET es de uso gratuito?
 Aspose.Words para .NET requiere una licencia. Puedes obtener una prueba gratuita[aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar más documentación sobre Aspose.Words para .NET?
 Puedes encontrar documentación detallada.[aquí](https://reference.aspose.com/words/net/).