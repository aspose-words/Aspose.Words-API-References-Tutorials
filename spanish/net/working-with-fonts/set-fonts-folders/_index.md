---
title: Establecer carpetas de fuentes
linktitle: Establecer carpetas de fuentes
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para configurar carpetas de fuentes al renderizar un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para configurar carpetas de fuentes al representar un documento con Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo especificar las carpetas de fuentes que se utilizarán al representar sus documentos con Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento renderizado editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta apropiada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Establecer fuentes de fuentes
 A continuación, puede establecer las fuentes de fuente utilizando el`FontSettings.DefaultInstance` clase y el`SetFontsSources()` método. En este ejemplo, estamos usando una fuente de fuente del sistema y una fuente de fuente de carpeta personalizada. Asegúrese de ajustar la ruta a la carpeta de fuentes personalizadas según sus necesidades.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Paso 3: Cargue el documento para renderizar
 Ahora puede cargar el documento para renderizar usando el`Document` clase. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 4: Guarde el documento renderizado
 Finalmente, puede guardar el documento renderizado en un archivo usando el`Save()` metodo de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Ejemplo de código fuente para Establecer carpetas de fuentes usando Aspose.Words para .NET 
```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{
		new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
	});
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo configurar carpetas de fuentes al renderizar un documento usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede especificar fácilmente las fuentes de fuentes que se utilizarán al renderizar sus documentos. Aspose.Words ofrece una API potente y flexible para trabajar con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar las fuentes de fuentes utilizadas al renderizar sus documentos según sus necesidades específicas.