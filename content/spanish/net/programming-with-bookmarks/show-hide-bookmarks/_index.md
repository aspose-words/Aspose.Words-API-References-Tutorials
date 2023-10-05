---
title: Mostrar Ocultar marcadores en un documento de Word
linktitle: Mostrar Ocultar marcadores en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a mostrar u ocultar un marcador específico en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/show-hide-bookmarks/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo utilizar la función Mostrar ocultar marcadores en la biblioteca Aspose.Words para .NET. Esta función le permite mostrar u ocultar un marcador específico en un documento de Word.

## Requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: cargar el documento

 Usamos el`Document` clase para cargar el documento existente desde un archivo:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Paso 2: mostrar u ocultar un marcador específico

 Usamos el`ShowHideBookmarkedContent`función para mostrar u ocultar un marcador específico en el documento. Esta función toma como parámetros el documento, el nombre del marcador y un booleano para indicar si mostrar u ocultar el marcador:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Paso 3: guardar el documento modificado

 Usamos el`Save` Método para guardar el documento modificado en un archivo:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Código fuente de ejemplo para Mostrar Ocultar marcadores usando Aspose.Words para .NET

Aquí está el código fuente de ejemplo completo para demostrar cómo mostrar u ocultar un marcador específico usando Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### MostrarHideBookmarkedContenido código fuente

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{MERGEFIELD favorito}" = "verdadero" "" ""}
            Field field = builder.InsertField("IF \"", null);
            builder.MoveTo(field.Start.NextSibling);
            builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
            builder.Write("\" = \"true\" ");
            builder.Write("\"");
            builder.Write("\"");
            builder.Write(" \"\"");

            Node currentNode = field.Start;
            bool flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.Run)
                    if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
                        flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
                currentNode = nextNode;
            }

            Node endNode = bm.BookmarkEnd;
            flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.FieldEnd)
                    flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
                endNode = currentNode;
                currentNode = nextNode;
            }

            doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });
        }
		
```
## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo utilizar la función Mostrar ocultar marcadores de Aspose.Words para .NET. Seguimos una guía paso a paso para mostrar u ocultar un marcador específico en un documento.

### Preguntas frecuentes para mostrar ocultar marcadores en un documento de Word

#### P: ¿Puedo mostrar u ocultar varios marcadores en el mismo documento?

R: Sí, puedes mostrar u ocultar varios marcadores en el mismo documento repitiendo los pasos 2 y 3 para cada marcador que quieras procesar.

#### P: ¿El código proporcionado funciona con otros formatos de documentos de Word, como .doc o .docm?

R: Sí, el código proporcionado funciona con varios formatos de documentos de Word compatibles con Aspose.Words, como .doc y .docm. Sólo asegúrese de utilizar el nombre de archivo y la ruta correctos al cargar y guardar el documento.

#### P: ¿Cómo puedo volver a mostrar un marcador oculto?

 R: Para volver a mostrar un marcador oculto, debe utilizar el mismo`ShowHideBookmarkedContent` función que pasa el valor`true` para el parámetro booleano que indica si se muestra u oculta el marcador.

#### P: ¿Puedo usar condiciones para mostrar u ocultar marcadores según los valores de los campos de combinación en el documento?

 R: Sí, puede utilizar condiciones y combinar valores de campos para determinar si un marcador debe mostrarse u ocultarse. Puedes personalizar el código del`ShowHideBookmarkedContent` función para tener en cuenta las condiciones y valores apropiados.

#### P: ¿Cómo puedo eliminar un marcador en un documento de Word usando Aspose.Words para .NET?

 R: Para eliminar un marcador en un documento de Word usando Aspose.Words para .NET, puede usar el`RemoveBookmarks` método de la`Document` clase. Aquí hay un código de muestra:

```csharp
doc.RemoveBookmarks("BookmarkName");
```