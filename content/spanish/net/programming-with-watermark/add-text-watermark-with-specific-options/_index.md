---
title: Agregar marca de agua de texto con opciones específicas
linktitle: Agregar marca de agua de texto con opciones específicas
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a agregar una marca de agua de texto con opciones específicas usando Aspose.Words para .NET. Guía paso por paso.
type: docs
weight: 10
url: /es/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

En este tutorial, le explicaremos cómo agregar una marca de agua de texto con opciones específicas usando Aspose.Words para .NET. Una marca de agua de texto es un texto superpuesto a un documento para indicar que es un borrador, confidencial, etc.

## Paso 1: usar un generador de documentos

Primero, usaremos un generador de documentos para agregar contenido a nuestro documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Paso 2: cargar el documento

Cargaremos un documento existente utilizando la ruta del documento.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Paso 3: agregue una marca de agua de texto con opciones específicas

 Crearemos una instancia del`TextWatermarkOptions`class y configure las opciones deseadas para la marca de agua del texto.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Paso 4: guarde el documento

Finalmente, podemos guardar el documento con la marca de agua de texto agregada.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Código fuente de ejemplo para agregar una marca de agua de texto con opciones específicas con Aspose.Words para .NET

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

¡Enhorabuena! Ahora ha aprendido cómo agregar marcas de agua de texto con opciones específicas usando Aspose.Words para .NET.

