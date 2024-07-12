---
title: Copiar texto marcado en un documento de Word
linktitle: Copiar texto marcado en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Copie sin esfuerzo texto marcado entre documentos de Word usando Aspose.Words para .NET. Aprenda cómo con esta guía paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/copy-bookmarked-text/
---
## Introducción

¿Alguna vez has necesitado copiar secciones específicas de un documento de Word a otro? ¡Pues estás de suerte! En este tutorial, le explicaremos cómo copiar texto marcado como favorito de un documento de Word a otro usando Aspose.Words para .NET. Ya sea que esté creando un informe dinámico o automatizando la generación de documentos, esta guía le simplificará el proceso.

## Requisitos previos

Antes de sumergirnos, asegúrese de tener lo siguiente:

-  Aspose.Words para la biblioteca .NET: puede descargarlo desde[aquí](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: Visual Studio o cualquier otro entorno de desarrollo .NET.
- Conocimientos básicos de C#: familiaridad con la programación en C# y .NET framework.

## Importar espacios de nombres

Para comenzar, asegúrese de tener importados los espacios de nombres necesarios en su proyecto:

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## Paso 1: cargue el documento fuente

Lo primero es lo primero: debe cargar el documento de origen que contiene el texto marcado que desea copiar.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 Aquí,`dataDir` es la ruta a su directorio de documentos, y`Bookmarks.docx` es el documento fuente.

## Paso 2: identificar el marcador

A continuación, identifique el marcador que desea copiar del documento fuente.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 Reemplazar`"MyBookmark1"` con el nombre real de su marcador.

## Paso 3: crear el documento de destino

Ahora, cree un nuevo documento donde se copiará el texto marcado.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Paso 4: Importar contenido marcado

 Para garantizar que se conserven los estilos y el formato, utilice`NodeImporter` para importar el contenido marcado como favorito desde el documento de origen al documento de destino.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## Paso 5: definir el método AppendBookmarkedText

Aquí es donde ocurre la magia. Defina un método para manejar la copia del texto marcado:

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## Paso 6: guarde el documento de destino

Finalmente, guarde el documento de destino para verificar el contenido copiado.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## Conclusión

¡Y eso es! Ha copiado con éxito el texto marcado como favorito de un documento de Word a otro usando Aspose.Words para .NET. Este método es potente para automatizar las tareas de manipulación de documentos, haciendo que su flujo de trabajo sea más eficiente y optimizado.

## Preguntas frecuentes

### ¿Puedo copiar varios marcadores a la vez?
Sí, puede recorrer varios marcadores y utilizar el mismo método para copiar cada uno.

### ¿Qué pasa si no se encuentra el marcador?
 El`Range.Bookmarks` la propiedad regresará`null`, así que asegúrese de manejar este caso para evitar excepciones.

### ¿Puedo conservar el formato del marcador original?
 ¡Absolutamente! Usando`ImportFormatMode.KeepSourceFormatting` garantiza que se conserve el formato original.

### ¿Existe un límite para el tamaño del texto marcado?
No hay un límite específico, pero el rendimiento puede variar con documentos extremadamente grandes.

### ¿Puedo copiar texto entre diferentes formatos de documentos de Word?
Sí, Aspose.Words admite varios formatos de Word y el método funciona en todos estos formatos.