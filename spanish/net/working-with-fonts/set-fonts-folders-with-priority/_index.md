---
title: Establecer carpetas de fuentes con prioridad
linktitle: Establecer carpetas de fuentes con prioridad
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para configurar carpetas de fuentes con prioridad al renderizar un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-with-priority/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para establecer carpetas de fuentes con prioridad al procesar un documento usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo especificar varias carpetas de fuentes con prioridad de búsqueda personalizada al representar sus documentos con Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento renderizado editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Establecer carpetas de fuentes con prioridad
 Luego puede configurar las carpetas de fuentes con prioridad usando el`FontSettings` clase y el`SetFontsSources()` método. Puede especificar varias fuentes de fuentes utilizando instancias de`SystemFontSource` y`FolderFontSource`. En este ejemplo, hemos definido dos orígenes de fuentes: el origen de fuentes del sistema predeterminado y una carpeta de fuentes personalizada con una prioridad de 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
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
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Ejemplo de código fuente para Establecer carpetas de fuentes con prioridad usando Aspose.Words para .NET 
```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo establecer carpetas de fuentes con prioridad al renderizar un documento usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede especificar fácilmente varias carpetas de fuentes con prioridad de búsqueda personalizada al renderizar sus documentos. Aspose.Words ofrece una API potente y flexible para trabajar con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar las fuentes de fuentes utilizadas al renderizar sus documentos según sus necesidades específicas.