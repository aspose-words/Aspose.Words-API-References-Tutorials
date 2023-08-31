---
title: Configurar enlace al contenido
linktitle: Configurar enlace al contenido
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para configurar enlaces al contenido de un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/configuring-link-to-content/
---

En este tutorial, lo guiaremos a través del código fuente de C# para configurar enlaces a contenido con Aspose.Words para .NET. Esta función le permite vincular a contenido específico en un documento.

## Paso 1: configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que en su proyecto se haga referencia a la biblioteca Aspose.Words para .NET.

## Paso 2: crear el documento y el constructor

En este paso crearemos un nuevo documento e inicializaremos el constructor. Utilice el siguiente código:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: crea un marcador

Ahora crearemos un marcador en el documento. Utilice el siguiente código para crear un marcador con texto dentro:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Este código crea un marcador llamado "MyBookmark" y agrega texto en su interior.

## Paso 4: configurar el enlace de contenido

Ahora configuraremos el enlace al contenido usando las propiedades del documento. Utilice el siguiente código para agregar y recuperar el enlace al contenido:

```csharp
// Obtenga la lista de todas las propiedades personalizadas en el documento.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Agregue una propiedad vinculada al contenido.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Este código agrega una propiedad relacionada con el contenido llamada "Marcador" con el marcador "MiMarcador". Luego, recupera información de propiedades relacionadas con el contenido, como el estado del enlace, el origen del enlace y el valor de la propiedad.

### Código fuente de ejemplo para configurar el enlace al contenido usando Aspose.Words para .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Recupere una lista de todas las propiedades del documento personalizado del archivo.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Agregar propiedad vinculada al contenido.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Ahora ha aprendido cómo configurar el enlace al contenido de un documento utilizando Aspose.Words para .NET. Si sigue la guía paso a paso proporcionada en este tutorial, puede crear y configurar fácilmente enlaces a contenido específico en sus propios documentos.