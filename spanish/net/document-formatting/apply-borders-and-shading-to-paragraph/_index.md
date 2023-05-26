---
title: Aplicar bordes y sombreado al párrafo
linktitle: Aplicar bordes y sombreado al párrafo
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a aplicar bordes y sombreado a un párrafo con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/apply-borders-and-shading-to-paragraph/
---

En este tutorial, le mostraremos cómo aplicar bordes y sombreado a un párrafo usando la funcionalidad de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios de formato.

## Paso 1: Crear y configurar el documento

Para comenzar, cree un nuevo documento y un objeto DocumentBuilder asociado. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: Configuración de bordes

Ahora configuremos los bordes del párrafo especificando el estilo de borde para cada lado. Así es cómo:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Paso 3: Configuración de relleno

Ahora configuraremos el relleno del párrafo especificando la textura y los colores de relleno. Así es cómo:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Paso 4: Agregar contenido

Vamos a agregar algo de contenido formateado al párrafo. Así es cómo:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Paso 3: Guardar el documento

 Después de insertar el campo de formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Código fuente de ejemplo para Aplicar bordes y sombreado a párrafo usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Aplicar bordes y sombreado al párrafo con Aspose.Words para .NET:

```csharp

	// La ruta al directorio de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```
