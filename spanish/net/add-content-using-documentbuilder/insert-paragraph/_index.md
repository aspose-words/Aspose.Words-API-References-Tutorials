---
title: Insertar párrafo
linktitle: Insertar párrafo
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar párrafos con formato en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-paragraph/
---

En este completo tutorial, aprenderá a insertar párrafos en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá agregar párrafos con formato a sus documentos.

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

## Paso 2: Establecer fuente y formato
A continuación, configure las propiedades de fuente y el formato de párrafo utilizando los objetos Font y ParagraphFormat respectivamente:

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## Paso 3: inserta un párrafo
Después de configurar la fuente y el formato, use el método Writeln de la clase DocumentBuilder para insertar un párrafo completo:

```csharp
builder.Writeln("A whole paragraph.");
```

## Paso 4: Guarde el documento
Después de insertar el párrafo, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Ejemplo de código fuente para insertar párrafo usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar un párrafo usando Aspose.Words para .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo insertar párrafos formateados en un documento de Word usando Aspose.Words para .NET. Al seguir la guía paso a paso y utilizar el código fuente provisto, ahora puede agregar párrafos personalizados con fuentes, formato y alineación específicos a sus documentos.