---
title: Reemplazar texto en pie de página
linktitle: Reemplazar texto en pie de página
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a reemplazar texto en el pie de página de documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/find-and-replace-text/replace-text-in-footer/
---

En este artículo, exploraremos el código fuente de C# anterior para comprender cómo usar la función Reemplazar texto en el pie de página en la biblioteca Aspose.Words para .NET. Esta función le permite buscar y reemplazar texto específico en los pies de página de los documentos de Word.

## requisitos previos

- Conocimientos básicos del lenguaje C#.
- Entorno de desarrollo .NET con la biblioteca Aspose.Words instalada.

## Paso 1: Cargue el documento

Antes de comenzar a usar el reemplazo de texto en el pie de página, debemos cargar el documento en Aspose.Words para .NET. Esto se puede hacer usando el`Document` class y especificando la ruta del archivo del documento:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

## Paso 2: Accede al pie de página

 Una vez cargado el documento, debemos acceder al pie de página para realizar el reemplazo del texto. En nuestro ejemplo, usamos el`HeadersFooters` propiedad de la primera sección del documento para obtener la colección de encabezados/pies de página. A continuación, seleccionamos el pie de página principal usando el`HeaderFooterType.FooterPrimary` índice:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

## Paso 3: Configure las opciones de búsqueda y reemplazo

 Ahora configuraremos las opciones de buscar y reemplazar usando un`FindReplaceOptions` objeto. En nuestro ejemplo, establecemos`MatchCase` a`false` ignorar mayúsculas y minúsculas al buscar, y`FindWholeWordsOnly` a`false` para permitir que se busquen y reemplacen partes de palabras:

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

## Paso 4: Reemplace el texto en el pie de página

 usamos el`Range.Replace` método para realizar el reemplazo de texto en el pie de página. En nuestro ejemplo, reemplazamos la frase "(C) 2006 Aspose Pty Ltd." por "Copyright (C) 2020 por Aspose Pty Ltd." :

```csharp
footer

.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

## Paso 5: Guarda el documento editado

 Finalmente, guardamos el documento modificado en un directorio específico usando el`Save` método:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
```

### Ejemplo de código fuente para Reemplazar texto en el pie de página usando Aspose.Words para .NET

Aquí está el código fuente de muestra completo para demostrar el uso del reemplazo de texto de pie de página con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Footer.docx");

	HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
	HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

	FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };

	footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
            
        
```

## Conclusión

En este artículo, exploramos el código fuente de C# para entender cómo usar la función Reemplazar texto en el pie de página de Aspose.Words para .NET. Seguimos una guía paso a paso para cargar un documento, acceder al pie de página, configurar las opciones de búsqueda y reemplazo, realizar el reemplazo de texto y guardar el documento editado.
