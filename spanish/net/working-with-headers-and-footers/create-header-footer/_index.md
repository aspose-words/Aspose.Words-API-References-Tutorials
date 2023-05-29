---
title: Crear encabezado de pie de página
linktitle: Crear encabezado de pie de página
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a crear encabezados y pies de página en sus documentos de Word con Aspose.Words para .NET. Personalice encabezados y pies de página para cada página.
type: docs
weight: 10
url: /es/net/working-with-headers-and-footers/create-header-footer/
---

Aquí hay una guía paso a paso para explicar el siguiente código fuente de C# para crear encabezados y pies de página usando la funcionalidad Aspose.Words para .NET. Asegúrese de haber incluido la biblioteca Aspose.Words en su proyecto antes de usar este código.

## Paso 1: establecer la ruta del directorio del documento

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Asegúrese de especificar la ruta correcta a su directorio de documentos donde se guardará el documento editado.

## Paso 2: Crear un documento y un generador de documentos

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aquí creamos una instancia de la`Document` clase y una instancia de la`DocumentBuilder` class que nos permitirá manipular el documento y añadir elementos.

## Paso 3: establece los parámetros de la página y el primer encabezado

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Especificar si queremos que los encabezados/pies de página de la primera página sean diferentes de las otras páginas.
// También puede usar la propiedad PageSetup.OddAndEvenPagesHeaderFooter para especificar
// diferentes encabezados/pies de página para páginas pares e impares.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Establecemos los parámetros de la página, incluida la distancia del encabezado, y luego pasamos al encabezado principal (`HeaderPrimary`). Usamos el generador de documentos para agregar texto y formatear el encabezado.

## Paso 4: Inserta una imagen y texto en el encabezado principal

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Usamos el generador de documentos para insertar una imagen en la esquina superior izquierda del encabezado principal, luego agregamos texto alineado a la derecha.

## Paso 5: Inserta una tabla en el pie de página principal

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## Paso 6: agregue una nueva página y establezca encabezados/pies de página

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//Esta sección no necesita un encabezado/pie de página diferente para la primera página, solo necesitamos una página de título en el documento,
// y el encabezado/pie de página de esta página ya se definió en la sección anterior.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Esta sección muestra los encabezados/pies de página de la sección anterior de forma predeterminada, llame a currentSection.HeadersFooters.LinkToPrevious(false) para romper este enlace,
// el ancho de página es diferente para la nueva sección, por lo que debemos establecer diferentes anchos de celda para una tabla de pie de página.
currentSection.HeadersFooters.LinkToPrevious(false);

// Si queremos utilizar los encabezados/pies de página ya existentes para esta sección,
// pero con algunos cambios menores, podría tener sentido copiar los encabezados/pies de página
// del apartado anterior y aplicar los cambios necesarios donde queramos.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Guardar el documento
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Agregamos un salto de página y un salto de sección para crear una nueva página donde los encabezados/pies de página principales serán visibles. Establecemos los parámetros para la nueva sección, luego usamos el`CopyHeadersFootersFromPreviousSection`para copiar los encabezados/pies de página de la sección anterior. Finalmente, establecemos los anchos de celda apropiados para la tabla de pie de página principal y guardamos el documento.

### Ejemplo de código fuente para crear encabezados y pies de página con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Especificar si queremos que los encabezados/pies de página de la primera página sean diferentes de otras páginas.
// También puede usar la propiedad PageSetup.OddAndEvenPagesHeaderFooter para especificar
// diferentes encabezados/pies de página para páginas pares e impares.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Inserte una imagen posicionada en la esquina superior izquierda del encabezado.
// La distancia desde los bordes superior/izquierdo de la página se establece en 10 puntos.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Usamos una tabla con dos celdas para hacer una parte del texto en la línea (con numeración de páginas).
// Para alinear a la izquierda, y la otra parte del texto (con derechos de autor) para alinear a la derecha.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Utiliza los campos PAGE y NUMPAGES para calcular automáticamente el número de página actual y muchas páginas.
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();

// Haga un salto de página para crear una segunda página en la que se verán los encabezados/pies de página principales.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//Esta sección no necesita un encabezado/pie de página diferente en la primera página, solo necesitamos una página de título en el documento,
// y el encabezado/pie de página de esta página ya se definió en la sección anterior.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Esta sección muestra encabezados/pies de página de la sección anterior
// por defecto llama a currentSection.HeadersFooters.LinkToPrevious(false) para cancelar el ancho de esta página
// es diferente para la nueva sección y, por lo tanto, debemos establecer diferentes anchos de celda para una tabla de pie de página.
currentSection.HeadersFooters.LinkToPrevious(false);

// Si queremos usar el conjunto de encabezado/pie de página ya existente para esta sección.
// Pero con algunas modificaciones menores, puede ser conveniente copiar encabezados/pies de página
// del apartado anterior y aplicar las modificaciones necesarias donde queramos.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```
