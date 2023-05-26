---
title: Especificar fuente predeterminada al renderizar
linktitle: Especificar fuente predeterminada al renderizar
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para especificar la fuente predeterminada al representar un documento con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/specify-default-font-when-rendering/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para especificar la fuente predeterminada al representar un documento con Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo especificar una fuente predeterminada para usar al renderizar sus documentos usando Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento renderizado editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta apropiada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento para renderizar
 A continuación, debe cargar el documento para renderizar utilizando el`Document` clase. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: Establecer fuente predeterminada
 Ahora puede especificar la fuente predeterminada que se usará al renderizar creando una instancia de la`FontSettings` clase y establecer el`DefaultFontName` propiedad de la`DefaultFontSubstitution` objetar a la`DefaultFontSubstitution` objeto`SubstitutionSettings` de`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Paso 4: Guarde el documento renderizado
 Finalmente, puede guardar el documento renderizado en un archivo usando el`Save()` metodo de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Ejemplo de código fuente para Especificar fuente predeterminada al renderizar usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Si la fuente predeterminada definida aquí no se puede encontrar durante el renderizado, entonces
	// en su lugar, se usa la fuente más cercana en la máquina.
	fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Conclusión
En este tutorial, aprendimos a especificar la fuente predeterminada al representar un documento con Aspose.Words para .NET. Al seguir esta guía paso a paso, puede configurar fácilmente una fuente predeterminada para usar al renderizar sus documentos. Aspose.Words ofrece una API potente y flexible para trabajar con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar la representación de sus documentos según sus necesidades específicas.