---
title: Mostrar Ocultar marcadores en un documento de Word
linktitle: Mostrar Ocultar marcadores en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a mostrar u ocultar un marcador específico en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/show-hide-bookmarks/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función Mostrar Ocultar Marcadores en la biblioteca Aspose.Words para .NET. Esta función le permite mostrar u ocultar un marcador específico en un documento de Word.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Cargar el documento

 usamos el`Document` clase para cargar el documento existente desde un archivo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Paso 2: Mostrar u ocultar un marcador específico

 usamos el`ShowHideBookmarkedContent` función para mostrar u ocultar un marcador específico en el documento. Esta función toma como parámetros el documento, el nombre del marcador y un booleano para indicar si mostrar u ocultar el marcador:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Paso 3: Guardar el documento modificado

 usamos el`Save` método para guardar el documento modificado en un archivo:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Ejemplo de código fuente para Mostrar Ocultar Marcadores usando Aspose.Words para .NET

Aquí está el código fuente de ejemplo completo para mostrar u ocultar un marcador específico usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

## Conclusión

En este artículo, exploramos el código fuente de C# para entender cómo usar la característica Mostrar Ocultar Marcadores de Aspose.Words para .NET. Seguimos una guía paso a paso para mostrar u ocultar un marcador específico en un documento.

### Preguntas frecuentes sobre mostrar ocultar marcadores en un documento de Word

#### P: ¿Puedo mostrar u ocultar varios marcadores en el mismo documento?

R: Sí, puede mostrar u ocultar varios marcadores en el mismo documento repitiendo los pasos 2 y 3 para cada marcador que desee procesar.

#### P: ¿El código proporcionado funciona con otros formatos de documentos de Word, como .doc o .docm?

R: Sí, el código proporcionado funciona con varios formatos de documentos de Word admitidos por Aspose.Words, como .doc y .docm. Solo asegúrese de usar el nombre de archivo y la ruta correctos al cargar y guardar el documento.

#### P: ¿Cómo puedo volver a mostrar un marcador oculto?

 R: Para volver a mostrar un marcador oculto, debe usar el mismo`ShowHideBookmarkedContent` función que pasa el valor`true`para el parámetro booleano que indica si mostrar u ocultar el marcador.

#### P: ¿Puedo usar condiciones para mostrar u ocultar marcadores en función de los valores de los campos de combinación en el documento?

 R: Sí, puede usar condiciones y combinar valores de campo para determinar si un marcador debe mostrarse u ocultarse. Puedes personalizar el código de la`ShowHideBookmarkedContent` para tener en cuenta las condiciones y los valores apropiados.

#### P: ¿Cómo puedo eliminar un marcador en un documento de Word usando Aspose.Words para .NET?

R: Para eliminar un marcador en un documento de Word usando Aspose.Words para .NET, puede usar el`RemoveBookmarks` metodo de la`Document`clase. Aquí hay un código de muestra:

```csharp
doc.RemoveBookmarks("BookmarkName");
```