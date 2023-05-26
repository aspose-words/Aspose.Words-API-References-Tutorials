---
title: Eliminar fila por marcador
linktitle: Eliminar fila por marcador
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a eliminar una fila de una tabla en función de un marcador específico en un documento mediante Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/delete-row-by-bookmark/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo usar la función Eliminar fila por marcador en la biblioteca Aspose.Words para .NET. Esta función le permite eliminar una fila de la tabla en función de un marcador específico en un documento.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Obtener el marcador

 usamos el`Bookmarks`propiedad del rango del documento para obtener el marcador específico que queremos usar para eliminar la fila de la tabla:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Paso 2: Eliminar la fila de la tabla

 usamos el`GetAncestor` método para obtener el`Row` escriba el elemento principal del marcador. A continuación, usamos el`Remove` método para eliminar la fila de la tabla:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Ejemplo de código fuente para Eliminar fila por marcador usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para demostrar cómo eliminar una fila de la tabla en función de un marcador específico usando Aspose.Words para .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Conclusión

En este artículo, hemos explorado el código fuente de C# para entender cómo usar la función Eliminar fila por marcador de Aspose.Words para .NET. Seguimos una guía paso a paso para eliminar una fila de la tabla en función de un marcador específico en un documento.