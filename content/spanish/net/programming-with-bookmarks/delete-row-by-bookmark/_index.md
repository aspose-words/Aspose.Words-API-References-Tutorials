---
title: Eliminar fila por marcador en un documento de Word
linktitle: Eliminar fila por marcador en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a eliminar una fila de una tabla según un marcador específico en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-bookmarks/delete-row-by-bookmark/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo utilizar la función Eliminar fila por marcador en Aspose.Words para la biblioteca .NET. Esta función le permite eliminar una fila de la tabla según un marcador específico en un documento de Word.

## Requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Obtener el marcador

 Usamos el`Bookmarks` propiedad del rango del documento para obtener el marcador específico que queremos usar para eliminar la fila de la tabla:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Paso 2: eliminar la fila de la tabla

 Usamos el`GetAncestor` método para obtener el`Row` escriba el elemento principal del marcador. A continuación, utilizamos el`Remove` método para eliminar la fila de la tabla:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Código fuente de ejemplo para Eliminar fila por marcador usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para demostrar cómo eliminar una fila de la tabla según un marcador específico usando Aspose.Words para .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Conclusión

En este artículo, hemos explorado el código fuente de C# para comprender cómo utilizar la función Eliminar fila por marcador de Aspose.Words para .NET. Seguimos una guía paso a paso para eliminar una fila de la tabla según un marcador específico en un documento.

### Preguntas frecuentes para eliminar fila por marcador en un documento de Word

#### P: ¿Puedo eliminar varias filas usando el mismo marcador?

R: Sí, puedes eliminar varias filas usando el mismo marcador. Sin embargo, debe manejar la lógica de su código para determinar la cantidad de filas que desea eliminar y realizar los ajustes necesarios en el fragmento de código proporcionado.

#### P: ¿Qué sucede si el marcador no existe en el documento?

R: Si el marcador especificado no existe en el documento, el fragmento de código devolverá un valor nulo para el objeto del marcador. Por lo tanto, debe manejar este escenario en su código agregando las comprobaciones adecuadas antes de intentar eliminar la fila de la tabla.

#### P: ¿La biblioteca Aspose.Words es de uso gratuito?

 R: La biblioteca Aspose.Words es una biblioteca comercial y es posible que necesite una licencia válida para usarla en sus proyectos. Puedes visitar el[Aspose.Words para referencias de API .NET](https://reference.aspose.com/words/net/) para obtener más información sobre sus opciones de licencia y precios.

#### P: ¿Puedo eliminar filas de una tabla en una sección específica del documento de Word?

R: Sí, puedes eliminar filas de una tabla en una sección específica de un documento de Word. Puede modificar el fragmento de código proporcionado para orientarlo a una sección específica utilizando el rango o marcador apropiado dentro de esa sección.