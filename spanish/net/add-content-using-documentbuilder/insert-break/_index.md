---
title: Insertar descanso
linktitle: Insertar descanso
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar saltos de página en documentos de Word usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-break/
---

En este completo ejemplo, aprenderá a insertar saltos de página en un documento de Word utilizando el método InsertBreak en Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá controlar los saltos de página dentro de su documento.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Insertar contenido y saltos de página
A continuación, utilice el método Writeln de la clase DocumentBuilder para agregar contenido al documento. Para insertar un salto de página, utilice el método InsertBreak con el parámetro BreakType.PageBreak:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## Paso 3: Guarde el documento
Después de insertar el contenido y los saltos de página, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Código fuente de ejemplo para Insertar ruptura usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar saltos de página usando Aspose.Words para .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

Recuerde ajustar el código de acuerdo con sus requisitos específicos y mejorarlo con funciones adicionales según sea necesario.


## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar saltos de página en un documento de Word usando Aspose.Words para .NET. Siguiendo la guía paso a paso y utilizando el código fuente proporcionado, ahora puede controlar la paginación y el diseño de su documento insertando saltos de página en las posiciones deseadas.
