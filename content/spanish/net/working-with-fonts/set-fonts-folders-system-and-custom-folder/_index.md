---
title: Establecer sistema de carpetas de fuentes y carpeta personalizada
linktitle: Establecer sistema de carpetas de fuentes y carpeta personalizada
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para configurar el sistema y las carpetas de fuentes personalizadas al renderizar un documento usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

En este tutorial, lo guiaremos paso a paso para configurar carpetas de fuentes del sistema y una carpeta personalizada al renderizar un documento usando Aspose.Words para .NET. Explicaremos el código fuente de C# incluido y le proporcionaremos una guía completa para ayudarle a comprender e implementar esta característica en sus propios proyectos. Al final de este tutorial, sabrá cómo especificar varias carpetas de fuentes, incluida la carpeta del sistema y una carpeta personalizada, para usarlas al renderizar sus documentos usando Aspose.Words para .NET.

## Paso 1: definir el directorio de documentos
Primero, debe establecer la ruta a su directorio de documentos. Esta es la ubicación donde desea guardar su documento renderizado editado. Reemplace "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: cargue el documento para renderizar
 Luego puede cargar el documento para renderizar usando el`Document` clase. Asegúrese de especificar la ruta correcta del documento.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: configurar el sistema y las carpetas de fuentes personalizadas
 Ahora puede configurar carpetas de fuentes del sistema y una carpeta personalizada usando el`FontSettings` clase y el`SetFontsSources()` método. Primero, necesita recuperar la lista de fuentes de fuentes dependientes del entorno usando`GetFontsSources()` y guárdelo en una lista. Luego puedes crear una nueva instancia de`FolderFontSource` especificando la ruta a la carpeta personalizada que contiene sus fuentes. Agregue esta instancia a la lista de fuentes de fuentes existentes. Finalmente, use`SetFontsSources()` para actualizar las fuentes de fuentes con la nueva lista.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Paso 4: aplicar la configuración de fuente
 A continuación, debe aplicar la configuración de fuente a su documento usando el`FontSettings` propiedad de la`Document` clase.

```csharp
doc.FontSettings = fontSettings;
```

## Paso 5: guarde el documento renderizado
Finalmente, puede guardar el documento renderizado en un archivo haciendo clic en

   utilizando el`Save()` método de la`Document` clase. Asegúrese de especificar la ruta y el nombre de archivo correctos.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Código fuente de muestra para establecer el sistema de carpetas de fuentes y una carpeta personalizada usando Aspose.Words para .NET 

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Recupere la variedad de fuentes de fuentes dependientes del entorno que se buscan de forma predeterminada.
// Por ejemplo, esto contendrá una fuente "Windows\Fonts\" en máquinas con Windows.
// Agregamos esta matriz a una nueva Lista para que agregar o eliminar entradas de fuentes sea mucho más fácil.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Agregue una nueva fuente de carpeta que le indicará a Aspose.Words que busque fuentes en la siguiente carpeta.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// Agregue la carpeta personalizada que contiene nuestras fuentes a la lista de fuentes de fuentes existentes.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusión
En este tutorial, aprendimos cómo configurar carpetas de fuentes del sistema y una carpeta personalizada al renderizar un documento usando Aspose.Words para .NET. Si sigue esta guía paso a paso, puede especificar fácilmente varias carpetas de fuentes, incluida la carpeta del sistema y una carpeta personalizada, para utilizarlas al renderizar sus documentos. Aspose.Words ofrece una API potente y flexible para el procesamiento de textos con fuentes en sus documentos. Con este conocimiento, puede controlar y personalizar las fuentes de fuentes utilizadas al representar sus documentos según sus necesidades específicas.

### Preguntas frecuentes

#### P: ¿Cómo puedo configurar las carpetas de fuentes del sistema en Aspose.Words?

R: Para configurar las carpetas de fuentes del sistema en Aspose.Words, no tiene que hacer nada. Aspose.Words utiliza automáticamente las fuentes del sistema instaladas en su sistema operativo.

#### P: ¿Cómo puedo configurar carpetas de fuentes personalizadas en Aspose.Words?

 R: Para configurar las carpetas de fuentes personalizadas en Aspose.Words, puede usar el`SetFontsFolders` método de la`Fonts` clase que especifica las ubicaciones de las carpetas de fuentes personalizadas.

#### P: ¿Puedo especificar varias carpetas de fuentes personalizadas en Aspose.Words?

 R: Sí, puede especificar varias carpetas de fuentes personalizadas en Aspose.Words usando el`SetFontsFolders` método de la`Fonts` clase con una lista de ubicaciones de carpetas.

#### P: ¿Cómo puedo comprobar las carpetas de fuentes definidas en Aspose.Words?

 Para verificar las carpetas de fuentes definidas en Aspose.Words, puede usar el`GetFolders` método de la`Fonts` class para obtener la lista de carpetas de fuentes configuradas.

#### P: ¿Las fuentes de carpetas personalizadas tienen prioridad sobre las fuentes del sistema en Aspose.Words?

R: Sí, las fuentes de carpetas personalizadas tienen prioridad sobre las fuentes del sistema en Aspose.Words. Si una fuente está presente tanto en carpetas personalizadas como en fuentes del sistema, Aspose.Words usará la versión de la carpeta personalizada.