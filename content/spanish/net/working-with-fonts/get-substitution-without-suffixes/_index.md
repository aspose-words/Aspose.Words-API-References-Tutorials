---
title: Obtener sustitución sin sufijos
linktitle: Obtener sustitución sin sufijos
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a administrar la sustitución de fuentes sin sufijos en Aspose.Words para .NET. Siga nuestra guía paso a paso para asegurarse de que sus documentos luzcan perfectos en todo momento.
type: docs
weight: 10
url: /es/net/working-with-fonts/get-substitution-without-suffixes/
---

Bienvenido a esta guía completa sobre cómo administrar la sustitución de fuentes usando Aspose.Words para .NET. Si alguna vez ha tenido problemas con las fuentes que no aparecen correctamente en sus documentos, ha venido al lugar correcto. Este tutorial lo llevará a través de un proceso paso a paso para manejar la sustitución de fuentes sin sufijos de manera eficiente. ¡Empecemos!

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de tener lo siguiente:

- Conocimientos básicos de C#: comprender la programación de C# hará que sea más fácil seguir e implementar los pasos.
-  Aspose.Words para la biblioteca .NET: descargue e instale la biblioteca desde[enlace de descarga](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: configure un entorno de desarrollo como Visual Studio para escribir y ejecutar su código.
-  Documento de muestra: Un documento de muestra (p. ej.,`Rendering.docx`) para trabajar durante este tutorial.

## Importar espacios de nombres

Primero, necesitamos importar los espacios de nombres necesarios para acceder a las clases y métodos proporcionados por Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using Aspose.Words.WarningInfo;
using System.Collections.Generic;
```

## Paso 1: definir el directorio de documentos

Para comenzar, especifique el directorio donde se encuentra su documento. Esto ayuda a localizar el documento en el que desea trabajar.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: configurar el controlador de advertencia de sustitución

A continuación, debemos configurar un controlador de advertencia que nos notificará cada vez que se produzca una sustitución de fuente durante el procesamiento del documento. Esto es crucial para detectar y manejar cualquier problema de fuente.

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## Paso 3: agregue fuentes de fuentes personalizadas

En este paso, agregaremos fuentes de fuentes personalizadas para garantizar que Aspose.Words pueda ubicar y usar las fuentes correctas. Esto es particularmente útil si tiene fuentes específicas almacenadas en directorios personalizados.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

En este código:
-  Recuperamos las fuentes de fuentes actuales y agregamos una nueva`FolderFontSource` apuntando a nuestro directorio de fuentes personalizadas (`C:\\MyFonts\\`).
- Luego actualizamos las fuentes de fuentes con esta nueva lista.

## Paso 4: guarde el documento

Finalmente, guarde el documento después de aplicar la configuración de sustitución de fuentes. Para este tutorial, lo guardaremos como PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## Paso 5: crear la clase de controlador de advertencias

Para manejar las advertencias de manera efectiva, cree una clase personalizada que implemente la`IWarningCallback` interfaz. Esta clase capturará y registrará cualquier advertencia de sustitución de fuentes.

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

En esta clase:
-  El`Warning` El método captura advertencias relacionadas con la sustitución de fuentes.
-  El`FontWarnings` La colección almacena estas advertencias para su posterior inspección o registro.

## Conclusión

Ahora domina el proceso de manejo de la sustitución de fuentes sin sufijos usando Aspose.Words para .NET. Este conocimiento garantizará que sus documentos mantengan la apariencia deseada, independientemente de las fuentes disponibles en el sistema. Siga experimentando con diferentes configuraciones y fuentes para aprovechar al máximo el poder de Aspose.Words.

## Preguntas frecuentes

### P1: ¿Cómo puedo utilizar fuentes de varios directorios personalizados?

 Puedes agregar varios`FolderFontSource` instancias a la`fontSources` enumere y actualice las fuentes de fuentes en consecuencia.

### P2: ¿Dónde puedo descargar una prueba gratuita de Aspose.Words para .NET?

 Puede descargar una prueba gratuita desde[Aspose página de prueba gratuita](https://releases.aspose.com/).

###  P3: ¿Puedo manejar varios tipos de advertencias usando`IWarningCallback`?

 Sí el`IWarningCallback` La interfaz le permite manejar varios tipos de advertencias, no solo la sustitución de fuentes.

### P4: ¿Dónde puedo obtener soporte para Aspose.Words?

 Para obtener ayuda, visite el[Foro de soporte de Aspose.Words](https://forum.aspose.com/c/words/8).

### P5: ¿Es posible adquirir una licencia temporal?

 Sí, puede obtener una licencia temporal del[página de licencia temporal](https://purchase.aspose.com/temporary-license/).