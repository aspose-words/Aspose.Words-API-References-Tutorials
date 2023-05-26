---
title: Desenredar marcadores de fila
linktitle: Desenredar marcadores de fila
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a desenredar marcadores de fila anidados para eliminar filas específicas sin afectar a otros marcadores.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/untangle-row-bookmarks/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función Untangle Row Bookmarks en la biblioteca Aspose.Words para .NET. Esta función permite poner los finales de los marcadores de las líneas en la misma línea que los comienzos de los marcadores.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Cargar el documento

 usamos el`Document` clase para cargar el documento existente desde un archivo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Paso 2: desentrañar marcadores de línea

 usamos el`Untangle` función para desenredar marcadores de filas. Esta función realiza la tarea personalizada de colocar los extremos de las líneas del marcador en la misma línea en la que comienza el marcador:

```csharp
Untangle(doc);
```

## Paso 3: Eliminar línea por marcador

 usamos el`DeleteRowByBookmark` función para eliminar una fila específica por su marcador:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Paso 4: Comprueba la integridad de otros marcadores

Verificamos que los otros marcadores no se hayan dañado comprobando si el final del marcador todavía está presente:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Ejemplo de código fuente para Untangle Row Bookmarks usando Aspose.Words para .NET**

Aquí está el código fuente de muestra completo para desenredar los marcadores de las líneas usando Aspose.Words para .NET:


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Esto realiza la tarea personalizada de colocar los extremos del marcador de fila en la misma fila con los inicios del marcador.
	Untangle(doc);

	// Ahora podemos eliminar fácilmente las filas de un marcador sin dañar los marcadores de ninguna otra fila.
	DeleteRowByBookmark(doc, "ROW2");

	// Esto es solo para verificar que el otro marcador no esté dañado.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

## Conclusión

En este artículo, exploramos el código fuente de C# para entender cómo usar la función Untangle Row Bookmarks de Aspose.Words para .NET. Seguimos una guía paso a paso para desenredar los marcadores de fila y eliminar una fila específica sin dañar otros marcadores.