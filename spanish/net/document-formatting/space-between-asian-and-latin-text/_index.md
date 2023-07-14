---
title: Espacio entre texto asiático y latino
linktitle: Espacio entre texto asiático y latino
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a ajustar automáticamente el espacio entre el texto asiático y latino en su documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/space-between-asian-and-latin-text/
---

En este tutorial, le mostraremos cómo usar la función Espacio entre texto asiático y latino con Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios.

## Paso 1: Crear y configurar el documento

Para comenzar, cree un nuevo documento y un objeto DocumentBuilder asociado. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: configurar el espacio entre el texto asiático y latino

Ahora configuraremos el espacio entre el texto asiático y latino usando las propiedades del objeto ParagraphFormat. Así es cómo:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Paso 3: Guardar el documento

 Después de insertar el campo de formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Ejemplo de código fuente para el espacio entre texto asiático y latino usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Espacio entre texto asiático y latino con Aspose.Words para .NET:


```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
	paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

	builder.Writeln("Automatically adjust space between Asian and Latin text");
	builder.Writeln("Automatically adjust space between Asian text and numbers");

	doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
        
```

Con este código podrá ajustar automáticamente el espacio entre el texto asiático y latino en su documento usando Aspose.Words para .NET.



