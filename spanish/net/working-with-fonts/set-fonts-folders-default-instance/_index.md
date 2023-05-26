---
title: Establecer instancia predeterminada de carpetas de fuentes
linktitle: Establecer instancia predeterminada de carpetas de fuentes
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para configurar la carpeta de fuentes predeterminada al renderizar un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-default-instance/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para configurar la carpeta de fuentes predeterminada al procesar un documento con Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo configurar la carpeta de fuentes predeterminada para usar al renderizar sus documentos usando Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento renderizado editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta apropiada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: establecer la carpeta de fuentes predeterminada
 Luego puede configurar la carpeta de fuentes predeterminada usando el`FontSettings.DefaultInstance` clase y el`SetFontsFolder()` método. Especifique la ruta a la carpeta de fuentes que desea usar como carpeta predeterminada.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Paso 3: Cargue el documento para renderizar
 Ahora puede cargar el documento para renderizar usando el`Document` clase. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 4: Guarde el documento renderizado
 Finalmente, puede guardar el documento renderizado en un archivo usando el`Save()` metodo de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Ejemplo de código fuente para establecer la instancia predeterminada de las carpetas de fuentes usando Aspose.Words para .NET 

```csharp
	// Ruta a su directorio de documentos
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo establecer la carpeta de fuentes predeterminada al representar un documento con Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede especificar fácilmente qué carpeta de fuentes usar como carpeta predeterminada al renderizar sus documentos. Aspose.Words ofrece una API potente y flexible para trabajar con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar las fuentes de fuentes utilizadas al renderizar sus documentos según sus necesidades específicas.