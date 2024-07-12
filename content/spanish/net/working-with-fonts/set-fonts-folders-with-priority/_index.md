---
title: Establecer carpetas de fuentes con prioridad
linktitle: Establecer carpetas de fuentes con prioridad
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para configurar carpetas de fuentes con prioridad al renderizar un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-with-priority/
---

En este tutorial, lo guiaremos a través del proceso paso a paso para configurar las carpetas de fuentes con prioridad al renderizar un documento usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarle a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo especificar varias carpetas de fuentes con prioridad de búsqueda personalizada al renderizar sus documentos usando Aspose.Words para .NET.

## Paso 1: definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento renderizado editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Establecer carpetas de fuentes con prioridad
 Luego puede configurar las carpetas de fuentes con prioridad usando el`FontSettings` clase y el`SetFontsSources()`método. Puede especificar múltiples fuentes de fuentes utilizando instancias de`SystemFontSource`y`FolderFontSource`. En este ejemplo, hemos definido dos fuentes de fuentes: la fuente de fuentes predeterminada del sistema y una carpeta de fuentes personalizada con una prioridad de 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Paso 3: cargue el documento para renderizar
 Ahora puede cargar el documento para renderizar usando el`Document` clase. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 4: guarde el documento renderizado
 Finalmente, puede guardar el documento renderizado en un archivo usando el`Save()` método de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Código fuente de muestra para establecer carpetas de fuentes con prioridad usando Aspose.Words para .NET 
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
En este tutorial, aprendimos cómo configurar las carpetas de fuentes con prioridad al renderizar un documento usando Aspose.Words para .NET. Si sigue esta guía paso a paso, podrá especificar fácilmente varias carpetas de fuentes con prioridad de búsqueda personalizada al representar sus documentos. Aspose.Words ofrece una API potente y flexible para el procesamiento de textos con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar las fuentes de fuentes utilizadas al representar sus documentos según sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Cómo puedo configurar las carpetas de fuentes con prioridad en Aspose.Words?

 R: Para configurar carpetas de fuentes con prioridad en Aspose.Words, puede usar el`SetFontsFoldersWithPriority` método de la`Fonts` clase especificando las ubicaciones de las carpetas de fuentes y su orden de prioridad.

#### P: ¿Qué sucede si una fuente está presente en varias carpetas con diferente prioridad?

R: Si una fuente está presente en varias carpetas con diferente prioridad, Aspose.Words utilizará la versión de la carpeta con mayor prioridad al procesar documentos.

#### P: ¿Puedo especificar varias carpetas de fuentes con la misma prioridad en Aspose.Words?

R: Sí, puede especificar varias carpetas de fuentes con la misma prioridad en Aspose.Words. Aspose.Words las considerará todas con igual prioridad al buscar fuentes en sus documentos.

#### P: ¿Cómo puedo verificar las carpetas de fuentes definidas con prioridad en Aspose.Words?

 R: Para verificar las carpetas de fuentes definidas con prioridad en Aspose.Words, puede usar el`GetFolders` método de la`Fonts` class para obtener la lista de carpetas de fuentes configuradas, incluido su orden de prioridad.

#### P: ¿De qué sirve configurar carpetas de fuentes con prioridad en Aspose.Words?

R: Configurar carpetas de fuentes con prioridad en Aspose.Words le permite controlar el orden de búsqueda de fuentes en sus documentos de Word. Esto le ayuda a garantizar que se utilicen las fuentes que desea y evitar problemas de sustitución de fuentes no deseadas.