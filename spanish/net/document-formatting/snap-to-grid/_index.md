---
title: Encajar a la cuadricula
linktitle: Encajar a la cuadricula
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para explicar el código fuente de C# de la función Snap to Grid con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/snap-to-grid/
---

En este tutorial, lo guiaremos a través de cómo usar la función Ajustar a la cuadrícula con Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios.

## Paso 1: Crear y configurar el documento

Para comenzar, cree un nuevo documento y un objeto DocumentBuilder asociado. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Alineación de cuadrícula

Ahora aplicaremos la alineación de cuadrícula a un párrafo específico y la fuente utilizada en el párrafo. Así es cómo:

```csharp
// Habilitar alineación de cuadrícula para el párrafo
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// Escribir texto en el párrafo.
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// Habilitar la alineación de cuadrícula para la fuente utilizada en el párrafo
par.Runs[0].Font.SnapToGrid = true;
```

## Paso 3: Guardar el documento

 Después de insertar el campo de formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### Ejemplo de código fuente para Ajustar a la cuadrícula usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Ajustar a la cuadrícula con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Optimice el diseño al escribir caracteres asiáticos.
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

Con este código, podrá alinear su texto con la cuadrícula y optimizar la apariencia de su documento usando Aspose.Words para .NET.

