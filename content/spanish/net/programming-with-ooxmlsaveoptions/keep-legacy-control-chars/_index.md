---
title: Mantener caracteres de control heredados
linktitle: Mantener caracteres de control heredados
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo conservar los caracteres de control heredados en documentos de Word usando Aspose.Words para .NET con esta guía paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---
## Introducción

¿Alguna vez te has sentido desconcertado por esos extraños e invisibles caracteres de control en tus documentos de Word? Son como pequeños duendes ocultos que pueden estropear el formato y la funcionalidad. Afortunadamente, Aspose.Words para .NET proporciona una función útil para mantener intactos estos caracteres de control heredados al guardar documentos. En este tutorial, profundizaremos en cómo administrar estos caracteres de control usando Aspose.Words para .NET. Lo desglosaremos paso a paso, asegurándonos de que comprenda cada detalle a lo largo del camino. ¿Listo para comenzar? ¡Vamos a sumergirnos!

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

1.  Aspose.Words para .NET: descargar e instalar desde[aquí](https://releases.aspose.com/words/net/).
2.  Una licencia Aspose válida: puede obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
3. Entorno de desarrollo: Visual Studio o cualquier otro IDE que admita .NET.
4. Conocimientos básicos de C#: será útil estar familiarizado con el lenguaje de programación C#.

## Importar espacios de nombres

Antes de escribir su código, debe importar los espacios de nombres necesarios. Agregue las siguientes líneas en la parte superior de su archivo C#:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Paso 1: configurar su proyecto

Primero, deberá configurar su proyecto en Visual Studio (o su IDE preferido). 

1. Cree un nuevo proyecto de C#: abra Visual Studio y cree un nuevo proyecto de aplicación de consola de C#.
2. Instale Aspose.Words para .NET: utilice el Administrador de paquetes NuGet para instalar Aspose.Words para .NET. Haga clic derecho en su proyecto en el Explorador de soluciones, seleccione "Administrar paquetes NuGet", busque "Aspose.Words" e instálelo.

## Paso 2: cargue su documento

A continuación, cargará el documento de Word que contiene los caracteres de control heredados.

1. Especifique la ruta del documento: establezca la ruta a su directorio de documentos.
   
   ```csharp
   string dataDir = "YOUR DOCUMENT DIRECTORY";
   ```

2.  Cargue el documento: utilice el`Document` clase para cargar su documento.

   ```csharp
   Document doc = new Document(dataDir + "Legacy control character.doc");
   ```

## Paso 3: configurar las opciones de guardar

Ahora, configuremos las opciones de guardado para mantener intactos los caracteres de control heredados.

1.  Crear opciones para guardar: inicializar una instancia de`OoxmlSaveOptions` y establecer el`KeepLegacyControlChars`propiedad a`true`.

   ```csharp
   OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc)
   {
       KeepLegacyControlChars = true
   };
   ```

## Paso 4: guarde el documento

Finalmente, guarde el documento con las opciones de guardado configuradas.

1.  Guarde el documento: utilice el`Save` método de la`Document` clase para guardar el documento con las opciones de guardado especificadas.

   ```csharp
   doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
   ```

## Conclusión

¡Y ahí lo tienes! Si sigue estos pasos, puede asegurarse de que sus caracteres de control heredados se conserven cuando trabaje con documentos de Word en Aspose.Words para .NET. Esta característica puede salvarle la vida, especialmente cuando se trata de documentos complejos donde los caracteres de control desempeñan un papel crucial. 

## Preguntas frecuentes

### ¿Qué son los personajes de control heredados?

Los caracteres de control heredados son caracteres no imprimibles que se utilizan en documentos antiguos para controlar el formato y el diseño.

### ¿Puedo eliminar estos caracteres de control en lugar de conservarlos?

Sí, puede utilizar Aspose.Words para .NET para eliminar o reemplazar estos caracteres si es necesario.

### ¿Esta función está disponible en todas las versiones de Aspose.Words para .NET?

Esta característica está disponible en versiones recientes. Asegúrese de utilizar la última versión para acceder a todas las funcionalidades.

### ¿Necesito una licencia para usar Aspose.Words para .NET?

 Sí, necesita una licencia válida. Puede obtener una licencia temporal para fines de evaluación.[aquí](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo encontrar más documentación sobre Aspose.Words para .NET?

 Puedes encontrar documentación detallada.[aquí](https://reference.aspose.com/words/net/).
 