---
title: Aplicar bordes y sombreado al párrafo en un documento de Word
linktitle: Aplicar bordes y sombreado al párrafo en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a aplicar bordes y sombreado a un párrafo en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
En este tutorial, le mostraremos cómo aplicar bordes y sombreado a un párrafo en un documento de Word usando la funcionalidad de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios de formato.

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

## Conclusión

En este tutorial, aprendimos cómo aplicar bordes y sombreado a un párrafo en un documento de Word usando Aspose.Words para .NET. Al configurar el párrafo`Borders` y`Shading` propiedades, pudimos establecer el estilo de borde, el color de línea y el color de relleno para el párrafo. Aspose.Words para .NET proporciona poderosas capacidades de formato para personalizar la apariencia de los párrafos y mejorar la representación visual de sus documentos.

### Preguntas frecuentes

#### P: ¿Cómo aplico bordes y sombreado a un párrafo en un documento de Word usando Aspose.Words para .NET?

R: Para aplicar bordes y sombreado a un párrafo en un documento de Word utilizando Aspose.Words para .NET, siga estos pasos:
1.  Crear un nuevo documento y un`DocumentBuilder` objeto.
2.  Configure los bordes del párrafo accediendo a la`Borders` propiedad de la`ParagraphFormat` y establecer el estilo de borde para cada lado.
3.  Configure el relleno de párrafos accediendo a la`Shading` propiedad de la`ParagraphFormat` y especificando la textura y los colores de relleno.
4.  Agregue contenido al párrafo usando el`Write` metodo de la`DocumentBuilder`.
5.  Guarde el documento usando el`Save` método.

#### P: ¿Cómo configuro el estilo del borde para cada lado del párrafo?

 R: Para establecer el estilo de borde para cada lado del párrafo, puede acceder a la`Borders` propiedad de la`ParagraphFormat` y establecer el`LineStyle` propiedad para cada`BorderType` (p.ej,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Puede especificar diferentes estilos de línea como`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, etc.

#### P: ¿Cómo especifico la textura y los colores de relleno para el sombreado del párrafo?

 R: Para especificar la textura y los colores de relleno para el sombreado del párrafo, puede acceder a la`Shading` propiedad de la`ParagraphFormat` y establecer el`Texture` propiedad a un índice de textura deseado (por ejemplo,`TextureIndex.TextureDiagonalCross` ). También puede configurar el`BackgroundPatternColor` y`ForegroundPatternColor` propiedades a los colores deseados usando el`System.Drawing.Color` clase.