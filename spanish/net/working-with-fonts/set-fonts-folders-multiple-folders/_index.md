---
title: Establecer carpetas de fuentes Múltiples carpetas
linktitle: Establecer carpetas de fuentes Múltiples carpetas
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para configurar varias carpetas de fuentes al renderizar un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para configurar varias carpetas de fuentes al representar un documento con Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarlo a comprender e implementar esta función en sus propios proyectos. Al final de este tutorial, sabrá cómo especificar varias carpetas de fuentes para usar al renderizar sus documentos usando Aspose.Words para .NET.

## Paso 1: Definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento renderizado editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Cargue el documento para renderizar
 Luego puede cargar el documento para renderizar usando el`Document` clase. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: Establecer carpetas de fuentes
 Ahora puede configurar múltiples carpetas de fuentes usando el`FontSettings` clase y el`SetFontsFolders()` método. Puede especificar las rutas a las carpetas de fuentes que desea usar en una matriz. En este ejemplo, hemos especificado dos carpetas de fuentes: "C:\MyFonts\" y "D:\Misc\Fuentes\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Paso 4: aplicar la configuración de fuente
 A continuación, debe aplicar la configuración de fuente a su documento utilizando el`FontSettings` propiedad de la`Document` clase.

```csharp
doc.FontSettings = fontSettings;
```

## Paso 5: Guarde el documento renderizado
 Finalmente, puede guardar el documento renderizado en un archivo usando el`Save()` metodo de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Ejemplo de código fuente para Establecer carpetas de fuentes Múltiples carpetas usando Aspose.Words para .NET 

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Tenga en cuenta que esta configuración anulará cualquier fuente de fuente predeterminada que se busque de forma predeterminada. Ahora solo se buscarán estas carpetas
// fuentes al renderizar o incrustar fuentes. Para agregar una fuente de fuente adicional mientras mantiene las fuentes de fuente del sistema, use FontSettings.GetFontSources y
// FontSettings.SetFontSources en su lugar.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Conclusión
En este tutorial, aprendimos a configurar varias carpetas de fuentes al representar un documento con Aspose.Words para .NET. Al seguir esta guía paso a paso, puede especificar fácilmente varias carpetas de fuentes para usar al renderizar sus documentos. Aspose.Words ofrece una API potente y flexible para trabajar con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar las fuentes de fuentes utilizadas al renderizar sus documentos según sus necesidades específicas.