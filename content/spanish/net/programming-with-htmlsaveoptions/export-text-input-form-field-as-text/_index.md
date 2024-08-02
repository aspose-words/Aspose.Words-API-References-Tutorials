---
title: Exportar campo de formulario de entrada de texto como texto
linktitle: Exportar campo de formulario de entrada de texto como texto
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a exportar campos de formulario de entrada de texto como texto sin formato usando Aspose.Words para .NET con esta guía completa paso a paso.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## Introducción

Entonces, ¿te estás sumergiendo en el mundo de Aspose.Words para .NET? Impresionante elección! Si buscas aprender cómo exportar un campo de formulario de entrada de texto como texto, estás en el lugar correcto. Ya sea que recién esté comenzando o mejorando sus habilidades, esta guía lo guiará a través de todo lo que necesita saber. Empecemos, ¿de acuerdo?

## Requisitos previos

Antes de profundizar en el meollo de la cuestión, asegurémonos de que tiene todo lo que necesita para seguirlo sin problemas:

-  Aspose.Words para .NET: descargue e instale la última versión desde[aquí](https://releases.aspose.com/words/net/).
- IDE: Visual Studio o cualquier entorno de desarrollo C#.
- Conocimientos básicos de C#: comprensión de la sintaxis básica de C# y conceptos de programación orientada a objetos.
- Documento: un documento de Word de muestra (`Rendering.docx`) con campos de formulario de entrada de texto.

## Importar espacios de nombres

Lo primero es lo primero: debe importar los espacios de nombres necesarios. Son como los componentes básicos que hacen que todo funcione a la perfección.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

Muy bien, ahora que tenemos nuestros espacios de nombres listos, ¡pasemos a la acción!

## Paso 1: configurar el proyecto

Antes de entrar en el código, asegurémonos de que nuestro proyecto esté configurado correctamente.

## Creando el proyecto

1. Abra Visual Studio: comience abriendo Visual Studio o su entorno de desarrollo C# preferido.
2.  Crear un nuevo proyecto: navegue hasta`File > New > Project` . Seleccionar`Console App (.NET Core)` o cualquier otro tipo de proyecto relevante.
3.  Nombra tu proyecto: dale a tu proyecto un nombre significativo, algo como`AsposeWordsExportExample`.

## Añadiendo Aspose.Words

1.  Administrar paquetes NuGet: haga clic derecho en su proyecto en el Explorador de soluciones y seleccione`Manage NuGet Packages`.
2.  Busque Aspose.Words: en el Administrador de paquetes NuGet, busque`Aspose.Words`.
3.  Instale Aspose.Words: haga clic en`Install` para agregar la biblioteca Aspose.Words a su proyecto.

## Paso 2: cargue el documento de Word

Ahora que nuestro proyecto está configurado, carguemos el documento de Word que contiene los campos del formulario de entrada de texto.

1. Especifique el directorio de documentos: defina la ruta al directorio donde está almacenado su documento.
2.  Cargue el documento: utilice el`Document` clase para cargar su documento de Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: preparar el directorio de exportación

Antes de exportar, asegurémonos de que nuestro directorio de exportación esté listo. Aquí es donde se guardarán nuestro archivo HTML y nuestras imágenes.

1. Defina el directorio de exportación: especifique la ruta donde se guardarán los archivos exportados.
2. Verifique y limpie el directorio: asegúrese de que el directorio exista y esté vacío.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## Paso 4: configurar las opciones de guardar

Aquí es donde ocurre la magia. Necesitamos configurar nuestras opciones de guardar para exportar el campo del formulario de entrada de texto como texto sin formato.

1.  Crear opciones para guardar: inicializar una nueva`HtmlSaveOptions` objeto.
2.  Establecer opción de exportación de texto: configure el`ExportTextInputFormFieldAsText`propiedad a`true`.
3. Establecer carpeta de imágenes: define la carpeta donde se guardarán las imágenes.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## Paso 5: guarde el documento como HTML

Finalmente, guardemos el documento de Word como un archivo HTML usando nuestras opciones de guardar configuradas.

1. Definir la ruta de salida: especifique la ruta donde se guardará el archivo HTML.
2.  Guarde el documento: utilice el`Save` método de la`Document`clase para exportar el documento.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## Conclusión

¡Y ahí lo tienes! Ha exportado con éxito un campo de formulario de entrada de texto como texto sin formato usando Aspose.Words para .NET. Esta guía debería haberle brindado un enfoque claro, paso a paso, para lograr esta tarea. Recuerde, la práctica hace la perfección, así que siga experimentando con diferentes opciones y configuraciones para ver qué más puede hacer con Aspose.Words.

## Preguntas frecuentes

### ¿Puedo exportar otros tipos de campos de formulario usando el mismo método?

 Sí, puedes exportar otros tipos de campos de formulario configurando diferentes propiedades del`HtmlSaveOptions` clase.

### ¿Qué pasa si mi documento tiene imágenes?

 Las imágenes se guardarán en la carpeta de imágenes especificada. Asegúrese de configurar el`ImagesFolder` propiedad en el`HtmlSaveOptions`.

### ¿Necesito una licencia para Aspose.Words?

 Sí, puedes obtener una prueba gratuita.[aquí](https://releases.aspose.com/) o comprar una licencia[aquí](https://purchase.aspose.com/buy).

### ¿Puedo personalizar el HTML exportado?

 ¡Absolutamente! Aspose.Words proporciona varias opciones para personalizar la salida HTML. Referirse a[documentación](https://reference.aspose.com/words/net/) para más detalles.

### ¿Aspose.Words es compatible con .NET Core?

Sí, Aspose.Words es compatible con .NET Core, .NET Framework y otras plataformas .NET.
