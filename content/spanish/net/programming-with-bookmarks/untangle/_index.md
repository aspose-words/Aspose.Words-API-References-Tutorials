---
title: Desenredar en un documento de Word
linktitle: Desenredar en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a desenredar los marcadores anidados en documentos de Word en filas de tablas adyacentes usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/untangle/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo usar la función Untangle en la biblioteca Aspose.Words para .NET. Esta función desenreda los marcadores anidados que se encuentran en filas de tabla adyacentes.

## Requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: buscar marcadores de documentos

Usamos un bucle foreach para recorrer todos los marcadores presentes en el documento:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Código para manejar marcadores aquí
}
```

## Paso 2: obtener filas principales de los marcadores

 Usamos el`GetAncestor` Métodos para recuperar las filas principales de los nodos inicial y final del marcador:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Paso 3: desenredar los marcadores anidados

Si se encuentran ambas líneas principales y el marcador comienza y termina en líneas adyacentes, movemos el nodo final del marcador al final del último párrafo de la última celda de la fila superior:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Código fuente de ejemplo para Untangle usando Aspose.Words para .NET

Aquí está el ejemplo de código fuente completo para desenredar marcadores anidados usando Aspose.Words para .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Obtenga la fila principal del marcador y del nodo final del marcador.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Si ambas filas se encuentran bien y el inicio y el final del marcador están contenidos en filas adyacentes,
		// mueva el nodo final del marcador al final del último párrafo en la última celda de la fila superior.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo utilizar la función Untangle de Aspose.Words para .NET. Hemos seguido una guía paso a paso para desenredar marcadores anidados en filas de tablas adyacentes.

### Preguntas frecuentes

#### P: ¿La función Desenredar solo funciona con marcadores anidados en filas de tabla adyacentes?

R: Sí, la función Desenredar está diseñada específicamente para desenredar marcadores anidados que se encuentran en filas de tablas adyacentes. Si los marcadores no están en líneas adyacentes, esta función no será aplicable.

#### P: ¿Cómo puedo identificar marcadores anidados en mi documento de Word?

R: Puede identificar marcadores anidados recorriendo los marcadores en el documento y comprobando si el marcador inicial y el marcador final están en filas adyacentes de la tabla. Puede utilizar el código fuente proporcionado en este artículo como punto de partida para implementar esta funcionalidad.

#### P: ¿La función Descifrar modifica el contenido del documento original?

R: Sí, la función Desenredar modifica el documento original moviendo el nodo final del marcador al final del último párrafo de la última celda de la fila superior. Asegúrese de guardar una copia de seguridad del documento antes de aplicar esta función.

#### P: ¿Cómo puedo desenredar los marcadores anidados en otros tipos de elementos del documento, como secciones o párrafos?

R: La función Desenredar presentada en este artículo está diseñada específicamente para desenredar marcadores anidados en filas de tablas adyacentes. Si desea desenredar los marcadores anidados en otros elementos del documento, deberá adaptar el código en consecuencia y utilizar los métodos adecuados para acceder a los elementos deseados.

#### P: ¿Existen otros métodos para desenredar los marcadores anidados en un documento de Word usando Aspose.Words para .NET?

 R: El método presentado en este artículo es un método común para desenredar marcadores anidados en filas de tablas adyacentes. Sin embargo, pueden existir otros enfoques o técnicas dependiendo de las necesidades específicas de su proyecto. Puedes consultar el[Aspose.Words para referencias de API .NET](https://reference.aspose.com/words/net/) para explorar más a fondo las funciones disponibles.