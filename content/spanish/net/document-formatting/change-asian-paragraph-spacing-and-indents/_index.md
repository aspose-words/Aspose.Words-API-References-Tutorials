---
title: Cambiar el espacio entre párrafos asiáticos y las sangrías en un documento de Word
linktitle: Cambiar el espacio entre párrafos asiáticos y las sangrías en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a cambiar el espacio entre párrafos asiáticos y las sangrías en un documento de Word con Aspose.Words para .NET.
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
format.CharacterUnitFirstLineIndent = 20; //Actualizar ParagraphFormat.FirstLineIndent
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
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent se actualizará
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore se actualizará
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter se actualizará

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Con este código podrá cambiar el espaciado y las sangrías de un párrafo asiático usando Aspose.Words para .NET.

## Conclusión

 En este tutorial, aprendimos cómo cambiar el espaciado y las sangrías de un párrafo asiático usando Aspose.Words para .NET. Al modificar las propiedades relevantes de la`ParagraphFormat`podemos controlar el diseño y la apariencia de los párrafos asiáticos en un documento de Word. Esta característica es útil para personalizar el formato de texto con caracteres asiáticos y lograr la presentación visual deseada en documentos con contenido de idiomas mixtos.

### Preguntas frecuentes

#### P: ¿Qué hace la función "Cambiar el espaciado y las sangrías de los párrafos asiáticos" en Aspose.Words para .NET?

R: La función "Cambiar espaciado y sangría de párrafo asiático" en Aspose.Words para .NET le permite modificar las propiedades de espaciado y sangría de un párrafo asiático en un documento de Word. Puede ajustar las sangrías izquierda y derecha, la sangría de la primera línea, el espacio antes y el espacio después de los valores para controlar el diseño y la apariencia del párrafo.

#### P: ¿Cómo cambio el espaciado y las sangrías de un párrafo asiático usando Aspose.Words para .NET?

 R: Para cambiar el espaciado y las sangrías de un párrafo asiático, debe acceder a la`ParagraphFormat`del párrafo de destino y modificar sus propiedades relevantes. En el código de ejemplo proporcionado, accedemos al primer párrafo del documento y establecemos el`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , y`LineUnitAfter` propiedades para ajustar el espaciado y las sangrías.

#### P: ¿Puedo aplicar estos cambios a otros párrafos del documento?

 R: Sí, puede aplicar estos cambios a otros párrafos del documento accediendo a sus respectivos`ParagraphFormat` objetos. El código de ejemplo apunta al primer párrafo del documento, pero puede modificar otros párrafos ajustando el índice en el`Paragraphs` colección o utilizando otros criterios para seleccionar los párrafos deseados.