---
title: Mostrar Ocultar contenido marcado en un documento de Word
linktitle: Mostrar Ocultar contenido marcado en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo mostrar y ocultar contenido marcado como favorito en documentos de Word usando Aspose.Words para .NET con esta guía detallada paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## Introducción

¿Listo para sumergirse en el mundo de la manipulación de documentos con Aspose.Words para .NET? Si eres un desarrollador que busca automatizar tareas de documentos o simplemente alguien curioso acerca del manejo de archivos de Word mediante programación, estás en el lugar correcto. Hoy, exploraremos cómo mostrar y ocultar contenido marcado como favorito en un documento de Word usando Aspose.Words para .NET. Esta guía paso a paso lo convertirá en un profesional en el control de la visibilidad del contenido según los marcadores. ¡Empecemos!

## Requisitos previos

Antes de entrar en el meollo de la cuestión, hay algunas cosas que necesitará:

1. Visual Studio: Cualquier versión compatible con .NET.
2.  Aspose.Words para .NET: Descárgalo[aquí](https://releases.aspose.com/words/net/).
3. Comprensión básica de C#: si puedes escribir un programa sencillo de "Hola mundo", estás listo.
4. Un documento de Word con marcadores: usaremos un documento de muestra con marcadores para este tutorial.

## Importar espacios de nombres

Primero lo primero, importemos los espacios de nombres necesarios. Esto garantiza que tengamos todas las herramientas que necesitamos para nuestra tarea.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

Con estos espacios de nombres implementados, estamos listos para comenzar nuestro viaje.

## Paso 1: configurar su proyecto

Muy bien, comencemos configurando nuestro proyecto en Visual Studio.

### Crear un nuevo proyecto

Abra Visual Studio y cree un nuevo proyecto de aplicación de consola (.NET Core). Nómbralo con algo atractivo, como "BookmarkVisibilityManager".

### Agregue Aspose.Words para .NET

Deberá agregar Aspose.Words para .NET a su proyecto. Puede hacer esto a través del Administrador de paquetes NuGet.

1. Vaya a Herramientas > Administrador de paquetes NuGet > Administrar paquetes NuGet para la solución.
2. Busque "Aspose.Words".
3. Instale el paquete.

¡Excelente! Ahora que nuestro proyecto está configurado, pasemos a cargar nuestro documento.

## Paso 2: cargar el documento

Necesitamos cargar el documento de Word que contiene los marcadores. Para este tutorial, usaremos un documento de muestra llamado "Bookmarks.docx".

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Este fragmento de código establece la ruta a su directorio de documentos y carga el documento en el`doc` objeto.

## Paso 3: Mostrar/Ocultar contenido marcado

Ahora viene la parte divertida: mostrar u ocultar el contenido según los marcadores. Crearemos un método llamado`ShowHideBookmarkedContent` para manejar esto.

Este es el método que alternará la visibilidad del contenido marcado como favorito:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### Desglose del método

-  Recuperación de marcadores:`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` recupera el marcador.
- Recorrido de nodos: Atravesamos los nodos dentro del marcador.
-  Alternar visibilidad: si el nodo es un`Run` (una secuencia de texto contigua), configuramos su`Hidden` propiedad.

## Paso 4: aplicar el método

Una vez implementado nuestro método, apliquémoslo para mostrar u ocultar contenido según un marcador.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

Esta línea de código ocultará el contenido del marcador denominado "MyBookmark1".

## Paso 5: guardar el documento

Finalmente, guardemos nuestro documento modificado.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

Esto guarda el documento con los cambios que hemos realizado.

## Conclusión

¡Y ahí lo tienes! Acaba de aprender cómo mostrar y ocultar contenido marcado como favorito en un documento de Word usando Aspose.Words para .NET. Esta poderosa herramienta facilita la manipulación de documentos, ya sea que esté automatizando informes, creando plantillas o simplemente modificando archivos de Word. ¡Feliz codificación!

## Preguntas frecuentes

### ¿Puedo alternar varios marcadores a la vez?
 Sí, puedes llamar al`ShowHideBookmarkedContent` método para cada marcador que desee alternar.

### ¿Ocultar contenido afecta la estructura del documento?
No, ocultar contenido sólo afecta a su visibilidad. El contenido permanece en el documento.

### ¿Puedo utilizar este método para otros tipos de contenido?
Este método alterna específicamente las ejecuciones de texto. Para otros tipos de contenido, deberá modificar la lógica de recorrido del nodo.

### ¿Aspose.Words para .NET es gratuito?
 Aspose.Words ofrece una prueba gratuita[aquí](https://releases.aspose.com/) , pero se requiere una licencia completa para uso en producción. puedes comprarlo[aquí](https://purchase.aspose.com/buy).

### ¿Cómo puedo obtener soporte si tengo problemas?
 Puede obtener apoyo de la comunidad Aspose[aquí](https://forum.aspose.com/c/words/8).