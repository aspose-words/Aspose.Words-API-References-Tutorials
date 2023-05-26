---
title: Configuración de enlace a contenido
linktitle: Configuración de enlace a contenido
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para configurar enlaces a contenido en un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-document-properties/configuring-link-to-content/
---

En este tutorial, lo guiaremos a través del código fuente de C# para configurar la vinculación al contenido con Aspose.Words para .NET. Esta característica le permite vincular contenido específico en un documento.

## Paso 1: Configuración del proyecto

Para comenzar, cree un nuevo proyecto de C# en su IDE favorito. Asegúrese de que se haga referencia a la biblioteca Aspose.Words para .NET en su proyecto.

## Paso 2: Creando el Documento y el Constructor

En este paso crearemos un nuevo documento e inicializaremos el constructor. Usa el siguiente código:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: crea un marcador

Ahora vamos a crear un marcador en el documento. Use el siguiente código para crear un marcador con texto dentro:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Este código crea un marcador llamado "MyBookmark" y agrega algo de texto dentro.

## Paso 4: configurar el enlace de contenido

Ahora configuraremos el enlace al contenido usando las propiedades del documento. Use el siguiente código para agregar y recuperar el enlace al contenido:

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

Este código agrega una propiedad relacionada con el contenido denominada "Marcador" con el marcador "MiMarcador". Luego, recupera información de propiedad relacionada con el contenido, como el estado del enlace, la fuente del enlace y el valor de la propiedad.

### Ejemplo de código fuente para configurar el enlace al contenido usando Aspose.Words para .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Recupere una lista de todas las propiedades de documentos personalizados del archivo.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Añadir vinculado a la propiedad de contenido.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Ahora aprendió cómo configurar el enlace al contenido en un documento usando Aspose.Words para .NET. Siguiendo la guía paso a paso proporcionada en este tutorial, puede crear y configurar fácilmente enlaces a contenido específico en sus propios documentos.