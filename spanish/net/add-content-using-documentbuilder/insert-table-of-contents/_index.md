---
title: Insertar tabla de contenido
linktitle: Insertar tabla de contenido
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar una tabla de contenido en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-table-of-contents/
---

En este completo tutorial, aprenderá cómo insertar una tabla de contenido en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá generar una tabla de contenido con encabezados y números de página apropiados.

## requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: Cree un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Document e inicialice un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: inserte una tabla de contenido
A continuación, utilice el método InsertTableOfContents de la clase DocumentBuilder para insertar una tabla de contenido. Especifique las opciones de formato requeridas dentro del método:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Paso 3: Agregar contenido del documento
Después de insertar la tabla de contenido, agregue el contenido real del documento. Establezca los estilos de encabezado apropiados usando StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Paso 4: actualice la tabla de contenido
La tabla de contenido recién insertada estará inicialmente vacía. Para completarlo, actualice los campos en el documento:

```csharp
doc.UpdateFields();
```

## Paso 5: Guarde el documento
Después de insertar la tabla de contenido y actualizar los campos, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Ejemplo de código fuente para insertar tabla de contenido usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar una tabla de contenido usando Aspose.Words para .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inicialice DocumentBuilder con el objeto Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar tabla de contenidoa
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Inicie el contenido real del documento en la segunda página.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// La tabla de contenido recién insertada estará inicialmente vacía.
// Debe completarse actualizando los campos en el documento.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```
