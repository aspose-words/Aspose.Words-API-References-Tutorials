---
title: Crear pie de página de encabezado
linktitle: Crear pie de página de encabezado
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear encabezados y pies de página en sus documentos de Word con Aspose.Words para .NET. Personalice encabezados y pies de página para cada página.
type: docs
weight: 10
url: /es/net/working-with-headers-and-footers/create-header-footer/
---

Aquí hay una guía paso a paso para explicar el siguiente código fuente de C# para crear encabezados y pies de página usando Aspose.Words para la funcionalidad .NET. Asegúrese de haber incluido la biblioteca Aspose.Words en su proyecto antes de usar este código.

## Paso 1: establecer la ruta del directorio de documentos

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Asegúrese de especificar la ruta correcta al directorio de documentos donde se guardará el documento editado.

## Paso 2: crear un documento y un generador de documentos

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aquí creamos una instancia del`Document` clase y una instancia de la`DocumentBuilder` clase que nos permitirá manipular el documento y agregar elementos.

## Paso 3: configurar los parámetros de la página y el primer encabezado

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Especificar si queremos que los encabezados/pies de página de la primera página sean diferentes al resto de páginas.
// También puede utilizar la propiedad PageSetup.OddAndEvenPagesHeaderFooter para especificar
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

Configuramos los parámetros de la página, incluida la distancia del encabezado, y luego pasamos al encabezado principal (`HeaderPrimary`). Usamos el generador de documentos para agregar texto y formatear el encabezado.

## Paso 4: inserta una imagen y un texto en el encabezado principal

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Usamos el generador de documentos para insertar una imagen en la esquina superior izquierda del encabezado principal, luego agregamos texto alineado a la derecha.

## Paso 5: inserta una tabla en el pie de página principal

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
// Esta sección no necesita un encabezado/pie de página diferente para la primera página, solo necesitamos una página de título en el documento.
// el encabezado/pie de página de esta página ya se ha definido en la sección anterior.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Esta sección muestra los encabezados y pies de página de la sección anterior de forma predeterminada, llame a currentSection.HeadersFooters.LinkToPrevious(false) para romper este enlace.
// el ancho de la página es diferente para la nueva sección, por lo que necesitamos establecer diferentes anchos de celda para una tabla de pie de página.
currentSection.HeadersFooters.LinkToPrevious(false);

// Si queremos utilizar los encabezados/pies de página ya existentes para esta sección,
//pero con algunos cambios menores, podría tener sentido copiar los encabezados y pies de página
// del apartado anterior y aplicar los cambios necesarios donde queramos.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// guardar el documento
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Agregamos un salto de página y un salto de sección para crear una nueva página donde los encabezados y pies de página principales serán visibles. Configuramos los parámetros para la nueva sección, luego usamos el`CopyHeadersFootersFromPreviousSection` método para copiar los encabezados/pies de página de la sección anterior. Finalmente, configuramos los anchos de celda apropiados para la tabla de pie de página principal y guardamos el documento.

### Código fuente de ejemplo para crear encabezados y pies de página con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Especifique si queremos que los encabezados/pies de página de la primera página sean diferentes de otras páginas.
// También puede utilizar la propiedad PageSetup.OddAndEvenPagesHeaderFooter para especificar
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

// Inserte una imagen posicionada en la esquina superior/izquierda del encabezado.
// La distancia desde los bordes superior/izquierdo de la página se establece en 10 puntos.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Usamos una tabla con dos celdas para hacer una parte del texto en la línea (con numeración de páginas).
// Alinear a la izquierda y la otra parte del texto (con copyright) alinear a la derecha.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Utiliza los campos PÁGINA y NUMPAGES para calcular automáticamente el número de página actual y muchas páginas.
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

// Haga un salto de página para crear una segunda página en la que se verán los encabezados y pies de página principales.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Esta sección no necesita un encabezado o pie de página diferente en la primera página, solo necesitamos una página de título en el documento.
// el encabezado/pie de página de esta página ya se ha definido en la sección anterior.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Esta sección muestra encabezados/pies de página de la sección anterior.
// de forma predeterminada, llame a currentSection.HeadersFooters.LinkToPrevious(false) para cancelar el ancho de esta página
// es diferente para la nueva sección y, por lo tanto, necesitamos establecer diferentes anchos de celda para una tabla de pie de página.
currentSection.HeadersFooters.LinkToPrevious(false);

// Si queremos utilizar el conjunto de encabezado/pie de página ya existente para esta sección.
// Pero con algunas modificaciones menores, puede resultar conveniente copiar encabezados y pies de página.
// del apartado anterior y aplicar las modificaciones necesarias donde queramos.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### Preguntas frecuentes

#### P: ¿Cómo puedo agregar un encabezado a mi documento en Aspose.Words?

 R: Para agregar un encabezado a su documento en Aspose.Words, puede usar el`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` método. Este método agrega un encabezado principal a la primera sección de su documento.

#### P: ¿Cómo puedo agregar un pie de página a mi documento en Aspose.Words?

 R: Para agregar un pie de página a su documento en Aspose.Words, puede usar el`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`método. Este método agrega un pie de página principal a la primera sección de su documento.

#### P: ¿Cómo puedo agregar texto a mi encabezado o pie de página en Aspose.Words?

 R: Para agregar texto a su encabezado o pie de página en Aspose.Words, puede usar el`HeaderFooter.Paragraphs` propiedad para obtener la colección de párrafos del encabezado o pie de página, luego agregue un párrafo que contenga su texto a esta colección usando la`ParagraphCollection.Add` método.

#### P: ¿Puedo personalizar el contenido del encabezado o pie de página con imágenes y números de página en Aspose.Words?

 R: Sí, puedes personalizar el contenido del encabezado o pie de página con imágenes y números de página en Aspose.Words. Puedes usar objetos como`Shape` para agregar imágenes y objetos como`Field` para agregar números de página a su encabezado o pie de página.

#### P: ¿Puedo cambiar la fuente, el tamaño y el color del texto en mi encabezado o pie de página en Aspose.Words?

 R: Sí, puedes cambiar la fuente, el tamaño y el color del texto en el encabezado o pie de página en Aspose.Words. Puede acceder a propiedades de formato de texto como`Font` para cambiar la fuente,`Size` para ajustar el tamaño, y`Color`para establecer el color del texto.