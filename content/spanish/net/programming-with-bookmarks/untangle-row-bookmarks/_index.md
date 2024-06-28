---
title: Desenredar marcadores de fila en un documento de Word
linktitle: Desenredar marcadores de fila en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a desenredar marcadores de filas anidadas en un documento de Word para eliminar filas específicas sin afectar otros marcadores.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/untangle-row-bookmarks/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo usar la función Untangle Row Bookmarks en la biblioteca Aspose.Words para .NET. Esta función permite colocar los finales de los marcadores de líneas en la misma línea que el comienzo de los marcadores.

## Requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: cargar el documento

 Usamos el`Document` clase para cargar el documento existente desde un archivo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Paso 2: Desenredar los marcadores de líneas

 Usamos el`Untangle` función para desenredar marcadores de filas. Esta función realiza la tarea personalizada de colocar los extremos de las líneas del marcador en la misma línea en la que comienza el marcador:

```csharp
Untangle(doc);
```

## Paso 3: eliminar línea por marcador

 Usamos el`DeleteRowByBookmark` función para eliminar una fila específica por su marcador:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Paso 4: Verifique la integridad de otros marcadores

Verificamos que los demás marcadores no hayan sido dañados comprobando si el final del marcador aún está presente:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Código fuente de ejemplo para Untangle Row Bookmarks usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para desenredar los marcadores de las líneas usando Aspose.Words para .NET:


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Esto realiza la tarea personalizada de colocar los extremos del marcador de fila en la misma fila donde comienza el marcador.
	Untangle(doc);

	// Ahora podemos eliminar fácilmente filas mediante un marcador sin dañar los marcadores de ninguna otra fila.
	DeleteRowByBookmark(doc, "ROW2");

	// Esto es sólo para comprobar que el otro marcador no esté dañado.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### Desenredar el código fuente
```csharp

private void Untangle(Document doc)
        {
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
        }

```

#### Código fuente de DeleteRowByBookmark
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo utilizar la función Untangle Row Bookmarks de Aspose.Words para .NET. Seguimos una guía paso a paso para desenredar los marcadores de filas y eliminar una fila específica sin dañar otros marcadores.

### Preguntas frecuentes para desenredar marcadores de fila en un documento de Word

#### P: ¿Descifrar marcadores de filas solo funciona con marcadores de filas en tablas?

R: Sí, la función Desenredar marcadores de filas está diseñada específicamente para desenredar marcadores de filas que se encuentran en tablas. Esta función se puede utilizar para procesar marcadores de línea en matrices y garantizar que los extremos de los marcadores estén en la misma línea que los inicios de los marcadores.

#### P: ¿La función Descodificar marcadores de líneas modifica el contenido del documento original?

R: Sí, la función Descifrar marcadores de línea modifica el documento original moviendo los finales de los marcadores de línea para colocarlos en la misma línea que el comienzo de los marcadores. Asegúrese de guardar una copia de seguridad del documento antes de aplicar esta función.

#### P: ¿Cómo puedo identificar marcadores de línea en mi documento de Word?

R: Los marcadores de filas se utilizan normalmente en tablas para marcar secciones específicas. Puede identificar marcadores de filas examinando los marcadores del documento y comprobando si están en las filas de la tabla.

#### P: ¿Es posible desenredar los marcadores de filas en tablas no adyacentes?

R: La función Desenredar marcadores de filas tal como se presenta en este artículo está diseñada para desenredar marcadores de filas en tablas adyacentes. Para desenredar los marcadores de filas en tablas no adyacentes, es posible que se requieran ajustes adicionales al código según la estructura del documento.

#### P: ¿Qué otras manipulaciones puedo realizar en los marcadores de filas una vez que se han desenredado?

R: Una vez que se desenredan los marcadores de línea, puede realizar diferentes manipulaciones según sea necesario. Esto puede incluir editar, eliminar o agregar contenido a líneas marcadas. Asegúrese de manejar los marcadores de línea con cuidado para evitar cualquier impacto no deseado en el resto del documento.