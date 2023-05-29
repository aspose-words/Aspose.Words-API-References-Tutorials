---
title: Marcador de inserción del Generador de documentos
linktitle: Marcador de inserción del Generador de documentos
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar marcadores en documentos de Word usando DocumentBuilder en Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---

En este completo ejemplo, aprenderá a insertar marcadores en un documento de Word usando la clase DocumentBuilder en Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá crear y administrar marcadores dentro de sus documentos.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: inserta un marcador
A continuación, utilice los métodos StartBookmark y EndBookmark de la clase DocumentBuilder para insertar un marcador en el documento. Proporcione un nombre único para el marcador como parámetro:

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## Paso 3: Guarde el documento
Después de insertar el marcador, guarde el documento en un archivo utilizando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### Ejemplo de código fuente para DocumentBuilder Insertar marcador usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar un marcador utilizando la clase DocumentBuilder en Aspose.Words para .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar marcadores en un documento de Word usando la clase DocumentBuilder en Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente provisto, ahora puede crear y administrar marcadores dentro de sus documentos.

Los marcadores son útiles para varios escenarios, como navegar a través de documentos grandes, hacer referencia a secciones específicas o manipular contenido mediante programación dentro de áreas marcadas.

Recuerde ajustar el código de acuerdo con sus requisitos específicos y mejorarlo con funciones adicionales según sea necesario.

