---
title: Cambiar el espaciado y las sangrías de los párrafos asiáticos
linktitle: Cambiar el espaciado y las sangrías de los párrafos asiáticos
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a cambiar el espacio entre párrafos asiáticos y las sangrías con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---

En este tutorial, lo guiaremos a través de cómo cambiar el espaciado y las sangrías de un párrafo asiático usando Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios.

## Paso 1: Cargar el documento

Para comenzar, especifique el directorio para sus documentos y cargue el documento que contiene la tipografía asiática en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Paso 2: cambiar el espacio entre párrafos y las sangrías

Ahora modificaremos el espaciado y las sangrías del primer párrafo del documento asiático. Así es cómo:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Actualizar ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Actualizar ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; // Actualizar ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Actualizar ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Actualizar ParagraphFormat.SpaceAfter
```

## Paso 3: Guardar el documento

 Después de insertar el campo de formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Ejemplo de código fuente para cambiar el espaciado y las sangrías de los párrafos asiáticos usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Editar espaciado entre párrafos asiáticos y sangrías con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent se actualizará
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent se actualizará
	format.CharacterUnitFirstLineIndent = 20;  //ParagraphFormat.FirstLineIndent se actualizará
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore se actualizará
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter se actualizará

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Con este código podrá cambiar el espaciado y las sangrías de un párrafo asiático usando Aspose.Words para .NET.

