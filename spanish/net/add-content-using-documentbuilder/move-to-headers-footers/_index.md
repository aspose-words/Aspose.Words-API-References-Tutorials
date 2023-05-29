---
title: Mover a Encabezados Pies de página
linktitle: Mover a Encabezados Pies de página
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar Aspose.Words para .NET para navegar y modificar encabezados y pies de página en documentos de Word con esta guía paso a paso.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/move-to-headers-footers/
---

En este ejemplo, exploraremos la función Mover a encabezados y pies de página de Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca de manipulación de documentos que permite a los desarrolladores crear, modificar y convertir documentos de Word mediante programación. La función Mover a encabezados/pies de página nos permite navegar a diferentes encabezados y pies de página dentro de un documento y agregarles contenido.

Repasemos el código fuente paso a paso para entender cómo usar la función Mover a encabezados/pies de página usando Aspose.Words para .NET.



## Paso 1: Inicializar el documento y el generador de documentos

Primero, inicialice los objetos Document y DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Configuración de encabezados y pies de página

Especifique la configuración de encabezado/pie de página para el documento. En este ejemplo, configuramos los encabezados y pies de página para que sean diferentes para la primera página y para las páginas pares/impares:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Paso 3: crear encabezados para diferentes páginas

Muévase a cada tipo de encabezado y agrégueles contenido. En este ejemplo, creamos encabezados para la primera página, las páginas pares y todas las demás páginas:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Paso 4: Creación de páginas en el documento
Agregue contenido al documento para crear varias páginas. Por ejemplo:

```csharp
// Cree dos páginas en el documento.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Paso 5: Guardar el documento

Guarde el documento modificado en la ubicación deseada:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Asegúrese de especificar la ruta y el formato de archivo adecuados (p. ej., DOCX).

### Ejemplo de código fuente para Mover a encabezados/pies de página usando Aspose.Words para .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Especifique que queremos encabezados y pies de página diferentes para las páginas primeras, pares e impares.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Crea los encabezados.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Cree dos páginas en el documento.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```
