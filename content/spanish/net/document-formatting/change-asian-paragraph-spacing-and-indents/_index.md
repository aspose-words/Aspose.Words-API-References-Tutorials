---
title: Cambiar el espaciado y la sangría de los párrafos asiáticos en un documento de Word
linktitle: Cambiar el espaciado y la sangría de los párrafos asiáticos en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a cambiar el espaciado y las sangrías de los párrafos asiáticos en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
En este tutorial, le explicaremos cómo cambiar el espaciado y las sangrías de un párrafo asiático usando Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios.

## Paso 1: cargar el documento

Para comenzar, especifique el directorio de sus documentos y cargue el documento que contiene la tipografía asiática en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Paso 2: cambiar el espaciado y la sangría de los párrafos

Modificaremos ahora el espaciado y las sangrías del primer párrafo del documento asiático. Así es cómo:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Actualizar ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Actualizar ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Actualizar ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Actualizar ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Actualizar ParagraphFormat.SpaceAfter
```

## Paso 3: guardar el documento

 Después de insertar el campo del formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Código fuente de ejemplo para cambiar el espaciado y sangría de párrafos asiáticos usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Editar sangrías y espaciado de párrafos asiáticos con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // Se actualizará ParagraphFormat.LeftIndent.
	format.CharacterUnitRightIndent = 10;      // Se actualizará ParagraphFormat.RightIndent.
	format.CharacterUnitFirstLineIndent = 20;  // Se actualizará ParagraphFormat.FirstLineIndent.
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore se actualizará
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter se actualizará

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Con este código podrás cambiar el espaciado y las sangrías de un párrafo asiático usando Aspose.Words para .NET.

## Conclusión

 En este tutorial, aprendimos cómo cambiar el espaciado y las sangrías de un párrafo asiático usando Aspose.Words para .NET. Modificando las propiedades relevantes del`ParagraphFormat`podemos controlar el diseño y la apariencia de los párrafos asiáticos en un documento de Word. Esta característica es útil para personalizar el formato del texto con caracteres asiáticos y lograr la presentación visual deseada en documentos con contenido de idiomas mixtos.

### Preguntas frecuentes

#### P: ¿Qué hace la función "Cambiar sangrías y espaciado de párrafos asiáticos" en Aspose.Words para .NET?

R: La función "Cambiar sangría y espaciado de párrafos asiáticos" en Aspose.Words para .NET le permite modificar las propiedades de espaciado y sangría de un párrafo asiático en un documento de Word. Puede ajustar los valores de sangría izquierda y derecha, sangría de primera línea, espacio antes y espacio después para controlar el diseño y la apariencia del párrafo.

#### P: ¿Cómo cambio el espaciado y las sangrías de un párrafo asiático usando Aspose.Words para .NET?

 R: Para cambiar el espaciado y las sangrías de un párrafo asiático, debe acceder a la`ParagraphFormat`del párrafo de destino y modificar sus propiedades relevantes. En el código de ejemplo proporcionado, accedemos al primer párrafo del documento y configuramos el`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , y`LineUnitAfter` propiedades para ajustar el espaciado y las sangrías.

#### P: ¿Puedo aplicar estos cambios a otros párrafos del documento?

 R: Sí, puedes aplicar estos cambios a otros párrafos del documento accediendo a sus respectivos`ParagraphFormat` objetos. El código de ejemplo se dirige al primer párrafo del documento, pero puede modificar otros párrafos ajustando el índice en el`Paragraphs` colección o utilizando otros criterios para seleccionar los párrafos deseados.