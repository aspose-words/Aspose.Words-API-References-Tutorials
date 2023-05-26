---
title: Desenredar
linktitle: Desenredar
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a desenredar marcadores anidados en filas de tablas adyacentes usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/untangle/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función Untangle en la biblioteca Aspose.Words para .NET. Esta función desentraña los marcadores anidados que se encuentran en filas de tablas adyacentes.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Explorar marcadores de documentos

Usamos un bucle foreach para recorrer todos los marcadores presentes en el documento:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Código para manejar marcadores aquí
}
```

## Paso 2: Obtener filas principales de marcadores

 usamos el`GetAncestor` métodos para recuperar las filas principales de los nodos inicial y final del marcador:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Paso 3: desenrede los marcadores anidados

Si se encuentran ambas líneas principales y el marcador comienza y termina en líneas adyacentes, movemos el nodo final del marcador al final del último párrafo de la última celda en la fila superior:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Ejemplo de código fuente para Untangle usando Aspose.Words para .NET

Aquí está el ejemplo de código fuente completo para desenredar marcadores anidados usando Aspose.Words para .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Obtenga la fila principal del marcador y del nodo final del marcador.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Si ambas filas se encuentran bien, y el inicio y el final del marcador están contenidos en filas adyacentes,
		// mueva el nodo final del marcador al final del último párrafo en la última celda de la fila superior.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Conclusión

En este artículo, exploramos el código fuente de C# para entender cómo usar la función Untangle de Aspose.Words para .NET. Hemos seguido una guía paso a paso para desenredar marcadores anidados en filas de tablas adyacentes.