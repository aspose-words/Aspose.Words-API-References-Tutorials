---
title: Mostrar Ocultar Marcadores
linktitle: Mostrar Ocultar Marcadores
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a mostrar u ocultar un marcador específico en un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/show-hide-bookmarks/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función Mostrar Ocultar Marcadores en la biblioteca Aspose.Words para .NET. Esta característica le permite mostrar u ocultar un marcador específico en un documento.

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