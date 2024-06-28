---
title: Mostrar Ocultar contenido marcado en un documento de Word
linktitle: Mostrar Ocultar contenido marcado en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a mostrar u ocultar dinámicamente contenido marcado en documentos de Word usando Aspose.Words para .NET con esta guía completa paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Introducción

¡Hola! ¿Alguna vez ha querido controlar la visibilidad de un contenido específico dentro de un documento de Word en función de determinadas condiciones? Con Aspose.Words para .NET, puede mostrar u ocultar dinámicamente contenido marcado como favorito con solo unas pocas líneas de código. En este tutorial, lo guiaré a través del proceso paso a paso, asegurándome de que comprenda cada parte del código. Al final, serás un profesional en la manipulación de marcadores en documentos de Word. ¡Empecemos!

## Requisitos previos

Antes de sumergirnos en el tutorial, asegurémonos de que tiene todo lo que necesita:

1. Conocimientos básicos de C#: debe sentirse cómodo con la sintaxis y los conceptos de C#.
2.  Aspose.Words para .NET: Descárgalo[aquí](https://releases.aspose.com/words/net/) . Si no está listo para comprar, puede comenzar con un[prueba gratis](https://releases.aspose.com/).
3. Visual Studio: cualquier versión reciente funcionará, pero se recomienda usar la última versión.
4. .NET Framework: asegúrese de que esté instalado en su máquina.

¿Listo para comenzar? ¡Excelente! Comencemos importando los espacios de nombres necesarios.

## Importar espacios de nombres

Para usar Aspose.Words para .NET, necesitamos importar los espacios de nombres requeridos. Este paso garantiza que tengamos acceso a todas las clases y métodos que usaremos.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Estos espacios de nombres son cruciales para trabajar con documentos de Word y manipular su contenido.

## Paso 1: configurar el documento

Primero, creemos un nuevo documento de Word y un generador de documentos. El creador de documentos nos ayuda a agregar y manipular fácilmente contenido dentro del documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

En este paso, inicializamos un nuevo documento y un generador de documentos. Esto configura nuestro entorno para futuras operaciones.

## Paso 2: Agregar contenido marcado

A continuación, agregaremos contenido al documento y crearemos un marcador a su alrededor. Este marcador nos ayudará a identificar y manipular el contenido.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Aquí, agregamos algo de texto antes y después del contenido marcado. El`StartBookmark` y`EndBookmark` Los métodos definen los límites del marcador.

## Paso 3: insertar un campo condicional

Para controlar la visibilidad del contenido marcado, usaremos un campo condicional. Este campo verificará una condición y mostrará u ocultará el contenido en consecuencia.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

En este paso, insertamos un campo IF que verifica el valor del marcador. Si el valor es "verdadero", mostrará "Visible"; de lo contrario, mostrará "Oculto".

## Paso 4: reorganizar los nodos

A continuación, debemos reorganizar los nodos para garantizar que la lógica condicional se aplique correctamente al contenido marcado.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
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
```

Aquí, movemos los nodos para asegurarnos de que la condición abarque adecuadamente el contenido marcado.

## Paso 5: Ejecutar la combinación de correspondencia

Finalmente, ejecutaremos una combinación de correspondencia para establecer el valor del marcador y determinar si el contenido debe mostrarse u ocultarse.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Este paso establece el valor del marcador en "verdadero", lo que hará que el contenido sea visible según nuestra condición.

## Paso 6: guardar el documento

Después de todas las manipulaciones, el último paso es guardar el documento modificado.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Aquí guardamos el documento con un nombre de archivo descriptivo para indicar los cambios.

## Conclusión

 ¡Y eso es! Ha aprendido con éxito cómo mostrar u ocultar contenido marcado como favorito en un documento de Word usando Aspose.Words para .NET. Este tutorial cubrió la creación de un documento, la adición de marcadores, la inserción de campos condicionales, la reorganización de nodos y la ejecución de una combinación de correspondencia. Aspose.Words ofrece una gran cantidad de funciones, así que no dude en explorar las[Documentación API](https://reference.aspose.com/words/net/) para capacidades más avanzadas.

## Preguntas frecuentes

### 1. ¿Qué es Aspose.Words para .NET?

Aspose.Words para .NET es una poderosa biblioteca que permite a los desarrolladores crear, modificar y convertir documentos de Word mediante programación. Es muy utilizado para tareas de automatización de documentos.

### 2. ¿Puedo utilizar Aspose.Words para .NET de forma gratuita?

 Puedes probar Aspose.Words para .NET usando un[prueba gratis](https://releases.aspose.com/). Para un uso prolongado, deberá adquirir una licencia.

### 3. ¿Cómo modifico otras propiedades de un marcador?

 Aspose.Words le permite manipular varias propiedades de un marcador, como su texto y ubicación. Referirse a[Documentación API](https://reference.aspose.com/words/net/) para obtener instrucciones detalladas.

### 4. ¿Cómo obtengo soporte para Aspose.Words para .NET?

Puede obtener soporte visitando el[Aspose foro de soporte](https://forum.aspose.com/c/words/8).

### 5. ¿Puedo manipular otros tipos de contenido con Aspose.Words para .NET?

Sí, Aspose.Words para .NET admite varios tipos de manipulación de contenido, incluidos texto, imágenes, tablas y más.