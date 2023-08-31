---
title: Control de contenido del cuadro de texto enriquecido
linktitle: Control de contenido del cuadro de texto enriquecido
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear un control de contenido de cuadro de texto enriquecido en un documento de Word utilizando Aspose.Words para .NET, lo que permite dar formato y estilo al texto.
type: docs
weight: 10
url: /es/net/programming-with-sdt/rich-text-box-content-control/
---

Este tutorial demuestra cómo crear un control de contenido de cuadro de texto enriquecido en un documento de Word usando Aspose.Words para .NET. Los controles de contenido del cuadro de texto enriquecido permiten a los usuarios ingresar y formatear texto con varios estilos y opciones de formato.

## Requisitos previos
Para seguir este tutorial, necesita tener lo siguiente:

- Aspose.Words para la biblioteca .NET instalada.
- Conocimientos básicos de C# y procesamiento de textos con documentos Word.

## Paso 1: configurar el directorio de documentos
 Comience configurando la ruta a su directorio de documentos. Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real al directorio donde desea guardar el documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: crear un documento y una etiqueta de documento estructurado
 Crear una nueva instancia del`Document` clase y un`StructuredDocumentTag` para representar el control de contenido del cuadro de texto enriquecido. Especificar`SdtType.RichText` como el tipo y`MarkupLevel.Block` como nivel de marcado para crear un cuadro de texto enriquecido a nivel de bloque.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Paso 3: crear y formatear el contenido de texto enriquecido
Cree un párrafo y ejecútelo para representar el contenido de texto enriquecido. Configure el texto y las opciones de formato, como color, fuente, etc.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Paso 4: agregue el contenido de texto enriquecido al control de contenido
Agregue el párrafo con el contenido de texto enriquecido al`ChildNodes` colección del control de contenido del cuadro de texto enriquecido.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Paso 5: agregue el control de contenido al documento
 Agregue el control de contenido del cuadro de texto enriquecido al cuerpo del documento usando el`AppendChild` método del cuerpo de la primera sección del documento.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Paso 6: guarde el documento
 Guarde el documento en el directorio especificado utilizando el`Save` método. Proporcione el nombre de archivo deseado con la extensión de archivo adecuada. En este ejemplo, guardamos el documento como "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Código fuente de ejemplo para el control de contenido de cuadro de texto enriquecido usando Aspose.Words para .NET 

```csharp
	//Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

¡Eso es todo! Ha creado con éxito un control de contenido de cuadro de texto enriquecido en su documento de Word utilizando Aspose.Words para .NET.