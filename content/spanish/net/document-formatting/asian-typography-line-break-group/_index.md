---
title: Grupo de salto de línea de tipografía asiática en documento de Word
linktitle: Grupo de salto de línea de tipografía asiática en documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a usar el grupo de salto de línea de tipografía asiática en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/asian-typography-line-break-group/
---
En este tutorial, le mostraremos cómo usar el grupo de salto de línea de tipografía asiática en la función de documento de Word con Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios de formato.

## Paso 1: Cargar el documento

Para comenzar, especifique el directorio para sus documentos y cargue el documento que contiene la tipografía asiática en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Paso 2: configuración de tipografía asiática

Ahora configuraremos los ajustes de tipografía asiática para el primer párrafo del documento. Así es cómo:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Paso 3: Guardar el documento

 Después de insertar el campo de formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Ejemplo de código fuente para Asian Typography Line Break Group usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Grupo de salto de línea de tipografía asiática con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Con este código, podrá aplicar el grupo de salto de línea de tipografía asiática usando Aspose.Words para .NET.

## Conclusión

 En este tutorial, exploramos la función "Grupo de salto de línea de tipografía asiática" en Aspose.Words para .NET. Al configurar el`FarEastLineBreakControl`, `WordWrap` , y`HangingPunctuation` propiedades de la`ParagraphFormat`, pudimos controlar el comportamiento de salto de línea para la tipografía asiática en un documento de Word. Esta característica es útil para manejar caracteres asiáticos y garantizar saltos de línea adecuados y ajuste de palabras en documentos con contenido de idiomas mixtos.

### Preguntas frecuentes

#### P: ¿Qué es la función "Grupo de salto de línea de tipografía asiática" en Aspose.Words para .NET?

R: La función "Grupo de salto de línea de tipografía asiática" en Aspose.Words para .NET le permite controlar el comportamiento de salto de línea para la tipografía asiática en un documento de Word. Específicamente, afecta cómo se dividen y ajustan las líneas cuando se trata de caracteres asiáticos en párrafos.

#### P: ¿Cómo habilito el "Grupo de salto de línea de tipografía asiática" en Aspose.Words para .NET?

 R: Para habilitar el "Grupo de salto de línea de tipografía asiática", debe configurar el`FarEastLineBreakControl`, `WordWrap` , y`HangingPunctuation` propiedades de la`ParagraphFormat` para el(los) párrafo(s) relevante(s) en su documento. Configuración`FarEastLineBreakControl` a`false` asegura que los caracteres asiáticos se traten de manera similar a los caracteres latinos con respecto a los saltos de línea.`WordWrap` ajustado a`true` permite el ajuste de palabras para la tipografía asiática, y`HangingPunctuation` ajustado a`false` evita que la puntuación se cuelgue en el texto asiático.

#### P: ¿Puedo aplicar el "Grupo de salto de línea de tipografía asiática" a párrafos específicos de un documento?

R: Sí, puede aplicar la configuración del "Grupo de salto de línea de tipografía asiática" a párrafos específicos en un documento de Word. En el código de ejemplo, la configuración se aplica al primer párrafo del documento. Puede ajustar el código para apuntar a otros párrafos según sea necesario accediendo a ellos a través de la`Paragraphs` colección de la(s) sección(es) relevante(s) en el documento.