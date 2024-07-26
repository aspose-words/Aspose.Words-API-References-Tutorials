---
title: Exportar recursos
linktitle: Exportar recursos
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a exportar recursos como CSS y fuentes mientras guarda documentos de Word como HTML usando Aspose.Words para .NET. Sigue nuestra guía paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/export-resources/
---
## Introducción

¡Hola, compañeros entusiastas de la tecnología! Si alguna vez has necesitado convertir documentos de Word a HTML, estás en el lugar correcto. Hoy nos sumergimos en el maravilloso mundo de Aspose.Words para .NET. Esta potente biblioteca facilita el trabajo con documentos de Word mediante programación. En este tutorial, recorreremos los pasos para exportar recursos, como fuentes y CSS, al guardar un documento de Word como HTML usando Aspose.Words para .NET. ¡Abróchese el cinturón para un viaje divertido e informativo!

## Requisitos previos

Antes de profundizar en el código, asegurémonos de que tiene todo lo que necesita para comenzar. Aquí hay una lista de verificación rápida:

1.  Visual Studio: asegúrese de tener Visual Studio instalado en su máquina. Puedes descargarlo desde el[Sitio web de Visual Studio](https://visualstudio.microsoft.com/).
2.  Aspose.Words para .NET: necesitará la biblioteca Aspose.Words para .NET. Si aún no lo tienes, obtén una prueba gratuita desde[Lanzamientos de Aspose](https://releases.aspose.com/words/net/) o comprarlo en el[Tienda Aspose](https://purchase.aspose.com/buy).
3. Conocimientos básicos de C#: una comprensión fundamental de C# le ayudará a seguir los ejemplos de código.

¿Tienes todo eso? ¡Excelente! Pasemos a importar los espacios de nombres necesarios.

## Importar espacios de nombres

Para utilizar Aspose.Words para .NET, debe incluir los espacios de nombres relevantes en su proyecto. Así es como lo haces:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Estos espacios de nombres son cruciales para acceder a las clases y métodos de Aspose.Words que usaremos en nuestro tutorial.

Analicemos el proceso de exportación de recursos al guardar un documento de Word como HTML. Lo iremos paso a paso para que sea fácil de seguir.

## Paso 1: configure su directorio de documentos

Lo primero es lo primero, debe especificar la ruta a su directorio de documentos. Aquí es donde se encuentra su documento de Word y donde se guardará el archivo HTML.

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio.

## Paso 2: cargue el documento de Word

 A continuación, carguemos el documento de Word que desea convertir a HTML. Para este tutorial, usaremos un documento llamado`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Esta línea de código carga el documento desde el directorio especificado.

## Paso 3: configurar las opciones de guardado de HTML

Para exportar recursos como CSS y fuentes, debe configurar el`HtmlSaveOptions`. Este paso es crucial para garantizar que su salida HTML esté bien estructurada e incluya los recursos necesarios.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://ejemplo.com/recursos"
};
```

Analicemos qué hace cada opción:
- `CssStyleSheetType = CssStyleSheetType.External`: Esta opción especifica que los estilos CSS deben guardarse en una hoja de estilo externa.
- `ExportFontResources = true`: Esto permite la exportación de recursos de fuentes.
- `ResourceFolder = dataDir + "Resources"`: Especifica la carpeta local donde se guardarán los recursos (como fuentes y archivos CSS).
- `ResourceFolderAlias = "http://example.com/resources"`: establece un alias para la carpeta de recursos, que se utilizará en el archivo HTML.

## Paso 4: guarde el documento como HTML

Con las opciones de guardar configuradas, el último paso es guardar el documento como un archivo HTML. Así es como lo haces:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Esta línea de código guarda el documento en formato HTML, junto con los recursos exportados.

## Conclusión

¡Y ahí lo tienes! Ha exportado recursos con éxito mientras guardaba un documento de Word como HTML usando Aspose.Words para .NET. Con esta poderosa biblioteca, manejar documentos de Word mediante programación se convierte en pan comido. Ya sea que esté trabajando en una aplicación web o simplemente necesite convertir documentos para usarlos sin conexión, Aspose.Words lo tiene cubierto.

## Preguntas frecuentes

### ¿Puedo exportar imágenes junto con fuentes y CSS?
 ¡Sí tu puedes! Aspose.Words para .NET también admite la exportación de imágenes. Sólo asegúrese de configurar el`HtmlSaveOptions` respectivamente.

### ¿Existe alguna forma de incrustar CSS en lugar de utilizar una hoja de estilo externa?
 Absolutamente. Puedes configurar`CssStyleSheetType` a`CssStyleSheetType.Embedded` si prefiere estilos incrustados.

### ¿Cómo puedo personalizar el nombre del archivo HTML de salida?
 Puede especificar cualquier nombre de archivo que desee en el`doc.Save` método. Por ejemplo,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### ¿Aspose.Words admite otros formatos además de HTML?
 Sí, admite varios formatos, incluidos PDF, DOCX, TXT y más. Revisar la[documentación](https://reference.aspose.com/words/net/) para obtener una lista completa.

### ¿Dónde puedo obtener más apoyo y recursos?
Para obtener más ayuda, visite el[Foro de soporte de Aspose.Words](https://forum.aspose.com/c/words/8) . También puede encontrar documentación detallada y ejemplos en el[Aspose sitio web](https://reference.aspose.com/words/net/).