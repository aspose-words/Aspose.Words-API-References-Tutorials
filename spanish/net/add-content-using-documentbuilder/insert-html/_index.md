---
title: Insertar HTML
linktitle: Insertar HTML
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar contenido HTML en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-html/
---

En este completo tutorial, aprenderá a insertar contenido HTML en un documento de Word utilizando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar elementos HTML, formato y estilos a sus documentos de Word.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Insertar contenido HTML
A continuación, utilice el método InsertHtml de la clase DocumentBuilder para insertar contenido HTML en el documento. Puede incluir etiquetas HTML, atributos y estilo dentro de la cadena HTML:

```csharp
builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");
```

## Paso 3: Guarde el documento
Después de insertar el contenido HTML, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

## Ejemplo de código fuente para insertar HTML usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar contenido HTML en un documento de Word usando Aspose.Words para .NET:
Esta característica es particularmente útil cuando tiene contenido HTML existente que desea incluir en sus documentos de Word mientras conserva el formato y el diseño originales.

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHtml(
		"<P align='right'>Paragraph right</P>" +
		"<b>Implicit paragraph left</b>" +
		"<div align='center'>Div center</div>" +
		"<h1 align='left'>Heading 1 left.</h1>");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
	
```

Recuerde ajustar el código de acuerdo con su contenido HTML y requisitos específicos. Asegúrese de que su HTML esté bien formado y sea compatible con Aspose.Words para .NET.

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar contenido HTML en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente provisto, ahora puede incorporar elementos HTML, formatos y estilos dentro de sus documentos de Word.


