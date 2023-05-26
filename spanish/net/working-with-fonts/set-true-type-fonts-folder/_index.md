---
title: Establecer carpeta de fuentes True Type
linktitle: Establecer carpeta de fuentes True Type
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para configurar la carpeta de fuentes True Type al renderizar un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-true-type-fonts-folder/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para configurar la carpeta de fuentes True Type al representar un documento con Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo especificar una carpeta personalizada que contenga fuentes True Type para usar cuando represente sus documentos usando Aspose.Words para .NET.

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

## Paso 3: Configurar la carpeta de fuentes True Type
 Ahora puede especificar la carpeta de fuentes de tipo verdadero para usar al renderizar creando una instancia de la`FontSettings` clase y usando el`SetFontsFolder()` método para establecer la carpeta de fuentes. Puede especificar una carpeta personalizada que contenga sus fuentes True Type. El segundo parámetro a`SetFontsFolder()` indica si también desea buscar subcarpetas de la carpeta especificada.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Paso 4: Guarde el documento renderizado
 Finalmente, puede guardar el documento renderizado en un archivo usando el`Save()` metodo de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Ejemplo de código fuente para establecer la carpeta de fuentes True Type usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Tenga en cuenta que esta configuración anulará cualquier fuente de fuente predeterminada que se busque de forma predeterminada. Ahora solo se buscarán estas carpetas
	// Fuentes al renderizar o incrustar fuentes. Para agregar una fuente de fuente adicional mientras mantiene las fuentes de fuente del sistema, use FontSettings.GetFontSources y
	// FontSettings.SetFontSources en su lugar
	fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
	// Establecer la configuración de fuente
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo configurar la carpeta de fuentes True Type al representar un documento con Aspose.Words para .NET. Al seguir esta guía paso a paso, puede especificar fácilmente una carpeta personalizada que contenga fuentes True Type para usar al renderizar sus documentos. Aspose.Words ofrece una API potente y flexible para trabajar con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar las fuentes utilizadas al renderizar sus documentos según sus necesidades específicas.