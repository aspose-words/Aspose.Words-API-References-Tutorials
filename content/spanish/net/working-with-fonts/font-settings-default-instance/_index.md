---
title: Instancia predeterminada de configuración de fuente
linktitle: Instancia predeterminada de configuración de fuente
second_title: API de procesamiento de documentos Aspose.Words
description: En este tutorial, aprenderá cómo configurar los ajustes de fuente predeterminados en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/font-settings-default-instance/
---

En este tutorial, le explicaremos cómo configurar los ajustes de fuente predeterminados en un documento de Word utilizando la biblioteca Aspose.Words para .NET. La configuración de fuente predeterminada le permite especificar las fuentes de fuente utilizadas al cargar y representar documentos. Lo guiaremos paso a paso para ayudarlo a comprender e implementar el código en su proyecto .NET.

## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes elementos:
- Un conocimiento práctico del lenguaje de programación C#.
- La biblioteca Aspose.Words para .NET instalada en su proyecto

## Paso 1: definir el directorio de documentos
 Primero, debe configurar la ruta del directorio a la ubicación de su documento de Word. Reemplazar`"YOUR DOCUMENT DIRECTORY"` en el código con la ruta apropiada.

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: configurar los ajustes de fuente predeterminados
 A continuación, crearemos una instancia de`FontSettings` usando`FontSettings.DefaultInstance`y luego especificaremos las fuentes de fuentes utilizadas al cargar y representar documentos. En este ejemplo, utilizamos una fuente de fuente del sistema y una fuente de fuente de carpeta.

```csharp
// Configurar los ajustes de fuente predeterminados
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Paso 3: cargue el documento con la configuración de fuente
 Ahora cargaremos el documento usando`LoadOptions` y especificar la configuración de fuente a utilizar.

```csharp
// Cargue el documento con la configuración de fuente.
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Código fuente de muestra para la instancia predeterminada de configuración de fuente usando Aspose.Words para .NET 
```csharp

//Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusión
En este tutorial, vimos cómo configurar los ajustes de fuente predeterminados en un documento de Word con Aspose.Words para .NET. Al especificar las fuentes de fuentes utilizadas al cargar y representar documentos, puede controlar la apariencia de las fuentes en sus documentos. No dudes en utilizar esta función para personalizar la configuración de fuentes en tus proyectos.

### Preguntas frecuentes

#### P: ¿Cómo puedo configurar la fuente predeterminada en Aspose.Words?

 R: Para configurar la fuente predeterminada en Aspose.Words, puede usar el`FontSettings` clase y el`DefaultFontName` propiedad que especifica el nombre de la fuente deseada.

#### P: ¿Puedo especificar el tamaño de fuente predeterminado en Aspose.Words?

 R: Sí, puede especificar el tamaño de fuente predeterminado en Aspose.Words usando el`DefaultFontSize` propiedad de la`FontSettings` clase. Puede establecer el tamaño de punto deseado.

#### P: ¿Es posible configurar el color de fuente predeterminado en Aspose.Words?

 R: Sí, puedes configurar el color de fuente predeterminado en Aspose.Words usando el`DefaultColor` propiedad de la`FontSettings` clase. Puede especificar el color utilizando valores RGB o nombres predefinidos.

#### P: ¿La configuración de fuente predeterminada se aplica a todos los documentos?

R: Sí, la configuración de fuente predeterminada se aplica a todos los documentos creados o editados en Aspose.Words, a menos que se establezcan configuraciones específicas para un documento individual.