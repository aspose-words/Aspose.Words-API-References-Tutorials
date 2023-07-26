---
title: Agregar texto marcado en un documento de Word
linktitle: Agregar texto marcado en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a agregar texto desde un marcador en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/append-bookmarked-text/
---

En este artículo, exploraremos el código fuente de C# anterior para entender cómo usar la función Agregar texto marcado en Aspose.Words para la biblioteca .NET. Esta característica le permite agregar el texto contenido en un marcador específico de un documento de Word a otro documento.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: obtener párrafos de Bookmark

 Antes de comenzar a agregar el texto del marcador, necesitamos obtener los párrafos que contienen el inicio y el final del marcador. Esto se puede hacer accediendo a la`BookmarkStart` y`BookmarkEnd` propiedades del marcador:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Paso 2: Verifique los párrafos principales

Comprobamos si los párrafos inicial y final tienen padres válidos, es decir, si realmente pertenecen a un párrafo. Si no, generamos una excepción:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Paso 3: Verifique los Padres de los Párrafos

Comprobamos si los párrafos inicial y final tienen el mismo padre. Si no, eso significa que los párrafos no están contenidos en la misma sección o documento, y estamos lanzando una excepción:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Paso 4: copiar párrafos

Iteramos a través de los nodos (párrafos) desde el párrafo inicial hasta el párrafo final. Para cada nodo, creamos una copia y la importamos al contexto del documento de destino:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Ejemplo de código fuente para agregar texto marcado usando Aspose.Words para .NET

Aquí está el código fuente de ejemplo completo para demostrar cómo agregar texto desde un marcador usando Aspose.Words para .NET:

```csharp

	// Este es el párrafo que contiene el comienzo del marcador.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Este es el párrafo que contiene el final del marcador.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Limitarnos a un escenario razonablemente simple.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Queremos copiar todos los párrafos desde el párrafo inicial hasta (e incluyendo) el párrafo final,
	// por lo tanto, el nodo en el que nos detenemos es uno después del párrafo final.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		// Esto crea una copia del nodo actual y lo importa (lo hace válido) en el contexto
		// del documento de destino. Importar significa ajustar correctamente los estilos y los identificadores de listas.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo usar la función Agregar texto marcado de Aspose.Words para .NET. Hemos seguido una guía paso a paso para obtener párrafos de un marcador, verificar a los padres y copiar párrafos a otro documento.

### Preguntas frecuentes para agregar texto marcado en un documento de Word

#### P1: ¿Cuáles son los requisitos previos para usar la función "Agregar texto con marcadores" en Aspose.Words para .NET?

R: Para usar la función "Agregar texto con marcadores" en Aspose.Words para .NET, debe tener conocimientos básicos del lenguaje C#. También necesita un entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

#### P2: ¿Cómo obtener los párrafos que contienen el principio y el final de un marcador en un documento de Word?

 R: Para obtener los párrafos que contienen el inicio y el final de un marcador en un documento de Word, puede acceder a la`BookmarkStart` y`BookmarkEnd` Propiedades del marcador. Aquí hay un código de muestra:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### P3: ¿Qué sucede si los párrafos inicial y final no tienen padres válidos?

R: Si los párrafos inicial y final no tienen padres válidos, es decir, no son realmente párrafos, se lanzará una excepción. Esta situación no se puede manejar en este momento.
