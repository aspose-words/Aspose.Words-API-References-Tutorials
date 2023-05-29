---
title: Insertar regla horizontal
linktitle: Insertar regla horizontal
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar reglas horizontales en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-horizontal-rule/
---

En este completo ejemplo, aprenderá a insertar una regla horizontal en un documento de Word utilizando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar reglas horizontales a sus documentos para la separación visual y la organización.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: inserte una regla horizontal
A continuación, utilice el método Writeln de la clase DocumentBuilder para agregar un texto descriptivo y luego inserte una regla horizontal:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Paso 3: Guarde el documento
Después de insertar la regla horizontal, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Código fuente de ejemplo para Insertar regla horizontal usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar una regla horizontal usando Aspose.Words para .NET:
Las reglas horizontales son útiles para varios escenarios, como dividir secciones, crear cortes visuales o resaltar información importante.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Recuerde ajustar el código de acuerdo con sus requisitos específicos y mejorarlo con funciones adicionales según sea necesario.

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar una regla horizontal en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente provisto, ahora puede separar y organizar visualmente sus documentos usando reglas horizontales.

