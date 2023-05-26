---
title: Acceder a marcadores
linktitle: Acceder a marcadores
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a acceder a los marcadores en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/access-bookmarks/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función de marcadores de acceso en la biblioteca Aspose.Words para .NET. Esta función brinda acceso a marcadores específicos en un documento de Word.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Cargar el documento

 Antes de comenzar a acceder a los marcadores, debemos cargar un documento de Word usando Aspose.Words para .NET. Esto se puede hacer instanciando un`Document` objeto que especifica la ruta del archivo del documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Paso 2: Acceso a marcadores

Una vez cargado el documento, podemos acceder a los marcadores en el documento. Hay dos formas de acceder a los marcadores: por índice y por nombre.

- Acceso por índice: En nuestro ejemplo, usamos el índice 0 para acceder al primer marcador del documento:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Acceso por nombre: En nuestro ejemplo, usamos el nombre "MyBookmark3" para acceder a un marcador específico en el documento:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Ejemplo de código fuente para Acceder a Marcadores usando Aspose.Words para .NET

Aquí está el código fuente de ejemplo completo para demostrar cómo acceder a los marcadores usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// Por índice:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// Por nombre:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo usar la característica Acceder a Marcadores de Aspose.Words para .NET. Seguimos una guía paso a paso para cargar un documento y acceder a los marcadores usando el índice y el nombre.