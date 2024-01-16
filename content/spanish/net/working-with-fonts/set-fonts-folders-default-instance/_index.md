---
title: Establecer instancia predeterminada de carpetas de fuentes
linktitle: Establecer instancia predeterminada de carpetas de fuentes
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para configurar la carpeta de fuentes predeterminada al renderizar un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-default-instance/
---

En este tutorial, lo guiaremos paso a paso para configurar la carpeta de fuentes predeterminada al renderizar un documento usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarle a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo configurar la carpeta de fuentes predeterminada para usar al renderizar sus documentos usando Aspose.Words para .NET.

## Paso 1: definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento renderizado editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: configurar la carpeta de fuentes predeterminada
Luego puede configurar la carpeta de fuentes predeterminada usando el`FontSettings.DefaultInstance` clase y el`SetFontsFolder()` método. Especifique la ruta a la carpeta de fuentes que desea utilizar como carpeta predeterminada.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Paso 3: cargue el documento para renderizar
 Ahora puede cargar el documento para renderizar usando el`Document` clase. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 4: guarde el documento renderizado
 Finalmente, puede guardar el documento renderizado en un archivo usando el`Save()` método de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Código fuente de muestra para establecer la instancia predeterminada de carpetas de fuentes usando Aspose.Words para .NET 

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo configurar la carpeta de fuentes predeterminada al renderizar un documento usando Aspose.Words para .NET. Siguiendo esta guía paso a paso, puede especificar fácilmente qué carpeta de fuentes usar como carpeta predeterminada al renderizar sus documentos. Aspose.Words ofrece una API potente y flexible para el procesamiento de textos con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar las fuentes de fuentes utilizadas al representar sus documentos según sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Cómo puedo configurar carpetas de fuentes predeterminadas en Aspose.Words?

 R: Para configurar carpetas de fuentes predeterminadas en Aspose.Words, debe usar el`Fonts` clase y el`SetFontsFolders` Método para especificar ubicaciones de carpetas de fuentes personalizadas.

#### P: ¿La configuración de carpetas de fuentes predeterminadas afecta a todos los documentos de Word procesados con Aspose.Words?

R: Sí, la configuración de carpetas de fuentes predeterminadas afecta a todos los documentos de Word procesados con Aspose.Words. Una vez que haya configurado las carpetas de fuentes predeterminadas, Aspose.Words usará estas ubicaciones para buscar fuentes en todos los documentos.

#### P: ¿Puedo configurar varias carpetas de fuentes predeterminadas en Aspose.Words?

 R: Sí, puede configurar varias carpetas de fuentes predeterminadas en Aspose.Words. Sólo necesita especificar las ubicaciones de las carpetas de fuentes personalizadas usando el`SetFontsFolders` método de la`Fonts` clase.

#### P: ¿Cómo puedo verificar las carpetas de fuentes predeterminadas actualmente configuradas en Aspose.Words?

 R: Para verificar las carpetas de fuentes predeterminadas actualmente definidas en Aspose.Words, puede usar el`GetFolders` método de la`Fonts` class para obtener las ubicaciones de las carpetas de fuentes configuradas.

#### P: ¿La configuración de carpetas de fuentes predeterminadas me permite usar fuentes personalizadas en mis documentos de Word?

R: Sí, al configurar carpetas de fuentes predeterminadas, puede usar fuentes personalizadas en sus documentos de Word. Sólo necesita colocar las fuentes en las carpetas especificadas y Aspose.Words las usará al generar o manipular los documentos.