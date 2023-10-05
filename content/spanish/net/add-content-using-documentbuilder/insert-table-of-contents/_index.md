---
title: Insertar tabla de contenidos en un documento de Word
linktitle: Insertar tabla de contenidos en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a insertar una tabla de contenido en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/insert-table-of-contents/
---
En este completo tutorial, aprenderá cómo insertar una tabla de contenido en un documento de Word usando Aspose.Words para .NET. Lo guiaremos a través del proceso y le proporcionaremos los fragmentos de código C# necesarios. Al final de esta guía, podrá generar una tabla de contenido con títulos y números de página adecuados.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Aspose.Words para la biblioteca .NET instalada en su sistema.

## Paso 1: crear un nuevo documento y DocumentBuilder
Para comenzar, cree un nuevo documento usando la clase Documento e inicialice un objeto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Insertar una tabla de contenido
A continuación, utilice el método InsertTableOfContents de la clase DocumentBuilder para insertar una tabla de contenido. Especifique las opciones de formato requeridas dentro del método:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Paso 3: agregar contenido del documento
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
La tabla de contenido recién insertada estará inicialmente vacía. Para completarlo, actualice los campos del documento:

```csharp
doc.UpdateFields();
```

## Paso 5: guarde el documento
Después de insertar la tabla de contenido y actualizar los campos, guarde el documento en un archivo usando el método Guardar de la clase Documento:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Código fuente de ejemplo para insertar tabla de contenido usando Aspose.Words para .NET
Aquí está el código fuente completo para insertar una tabla de contenido usando Aspose.Words para .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Inicializar DocumentBuilder con el objeto Documento
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insertar tabla de contenido
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Comience el contenido real del documento en la segunda página.
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
// Debe completarse actualizando los campos del documento.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo insertar una tabla de contenido en un documento de Word usando Aspose.Words para .NET. Si sigue esta guía paso a paso y utiliza el código fuente proporcionado, ahora puede generar una tabla de contenido con encabezados y números de página adecuados para sus documentos.

### Preguntas frecuentes para insertar tabla de contenido en un documento de Word

#### P: ¿Puedo personalizar la apariencia de la tabla de contenido?

 R: Sí, puede personalizar la apariencia de la tabla de contenido modificando las opciones de formato especificadas en el`InsertTableOfContents` método. Los parámetros le permiten controlar los números de página, la sangría y otros estilos.

#### P: ¿Qué sucede si quiero incluir niveles de encabezado específicos en la tabla de contenido?

 R: Puede especificar los niveles de encabezado que desea incluir en la tabla de contenido ajustando el valor dentro del`InsertTableOfContents` método. Por ejemplo, usando`"\\o \"1-3\""` incluirá los niveles de encabezado 1 a 3.

#### P: ¿Puedo actualizar la tabla de contenido automáticamente si hago cambios en el contenido del documento?

 R: Sí, puedes actualizar la tabla de contenido automáticamente llamando al`UpdateFields` método en el documento. Esto garantizará que cualquier cambio realizado en el contenido del documento, como agregar o eliminar encabezados, se refleje en la tabla de contenido.

#### P: ¿Cómo puedo aplicar un estilo diferente a los niveles de encabezado en la tabla de contenido?

 R: Puede diseñar los niveles de título de manera diferente utilizando diferentes estilos de párrafo para cada nivel de título. Al asignar diferentes`StyleIdentifier` valores a la`ParagraphFormat` del`DocumentBuilder`, puede crear estilos distintos para cada nivel de título.

#### P: ¿Es posible agregar formato adicional a los títulos de la tabla de contenido?

 R: Sí, puede agregar formato adicional a los títulos de la tabla de contenido, como estilos de fuente, colores u otras propiedades. Al ajustar el`Font` propiedades de la`DocumentBuilder`, puede aplicar formato personalizado a los encabezados.