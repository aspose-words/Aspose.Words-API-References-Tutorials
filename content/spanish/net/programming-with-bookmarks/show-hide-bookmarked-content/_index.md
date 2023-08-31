---
title: Mostrar Ocultar contenido marcado en un documento de Word
linktitle: Mostrar Ocultar contenido marcado en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a mostrar u ocultar el contenido de los marcadores en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo utilizar la función Mostrar ocultar contenido marcado en Aspose.Words para la biblioteca .NET. Esta función le permite mostrar u ocultar el contenido de un marcador en un documento de Word según una condición específica al fusionar datos.

## Requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Obtener el marcador

 Usamos el`Bookmarks` propiedad del rango del documento para obtener el marcador específico sobre el que queremos mostrar u ocultar el contenido:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Paso 2: insertar los campos de combinación

 Usamos un generador de documentos.`DocumentBuilder` para insertar los campos de combinación necesarios. Estos campos de combinación establecerán una condición para mostrar u ocultar el contenido del marcador dependiendo del valor del`showHide` variable:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Paso 3: mover el contenido del marcador

Recorremos el contenido del marcador y lo movemos para que aparezca.

isse antes del marcador. Esto controlará mostrar u ocultar contenido según la condición especificada:

```csharp
Node currentNode = field. Start;
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
```

## Paso 4: mover el resto del contenido del marcador

Movemos el resto del contenido del marcador después del marcador, utilizando el nodo final del marcador como punto de inserción:

```csharp
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
```

## Paso 5: Realizar la fusión

 Usamos el`Execute` método del documento`s `Unificación de correo` object to execute the merge using the bookmark name and the value of the `mostrarHide`variable:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Código fuente de ejemplo para Mostrar ocultar contenido marcado usando Aspose.Words para .NET

Aquí está el ejemplo completo del código fuente para demostrar cómo mostrar u ocultar el contenido de los marcadores usando Aspose.Words para .NET:

```csharp

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

```

## Conclusión

En este artículo, exploramos el código fuente de C# para comprender cómo utilizar la función Mostrar ocultar contenido marcado como favorito de Aspose.Words para .NET. Hemos seguido una guía paso a paso para mostrar u ocultar el contenido de un marcador según una condición específica al fusionar datos.

### Preguntas frecuentes para mostrar ocultar contenido marcado en un documento de Word

#### P: ¿Puedo utilizar la misma condición para varios marcadores en el mismo documento?

 R: Sí, puedes utilizar la misma condición para varios marcadores en el mismo documento. Simplemente repita los pasos 2 a 5 para cada marcador, ajustando el nombre del marcador y, opcionalmente, el valor del`showhide` variables según sea necesario.

#### P: ¿Cómo puedo agregar más condiciones para mostrar u ocultar el contenido de los marcadores?

 R: Para agregar más condiciones, puede usar operadores lógicos como`AND` y`OR` en el código para insertar los campos de combinación en el paso 2. Edite la condición en el siguiente código para agregar condiciones adicionales:

```csharp
builder. Write("\" = \"true\" ");
```

#### P: ¿Cómo puedo eliminar un marcador en un documento de Word usando Aspose.Words para .NET?

R: Para eliminar un marcador en un documento de Word usando Aspose.Words para .NET, puede usar el`Remove` método de la`Bookmarks` colección del rango de documentos. Aquí hay un código de muestra para eliminar un marcador específico:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### P: ¿La biblioteca Aspose.Words es gratuita?

 R: La biblioteca Aspose.Words es una biblioteca comercial y requiere una licencia válida para usarla en sus proyectos. Puedes comprobar[Aspose.Words para referencias de API .NET](https://reference.aspose.com/words/net/) para obtener más información sobre las opciones de licencia y los precios.

#### P: ¿Hay otras bibliotecas disponibles para el procesamiento de textos con documentos de Word en .NET?

R: Sí, hay otras bibliotecas disponibles para el procesamiento de textos con documentos de Word en .NET, como Open XML SDK y GemBox.Document. Puede explorar estas bibliotecas como alternativas a Aspose.Words según sus necesidades y preferencias específicas.