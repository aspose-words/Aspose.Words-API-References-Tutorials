---
title: Agregar prefijo de nombre de clase CSS
linktitle: Agregar prefijo de nombre de clase CSS
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo agregar un prefijo de nombre de clase CSS al guardar documentos de Word como HTML usando Aspose.Words para .NET. Se incluyen guía paso a paso, fragmentos de código y preguntas frecuentes.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## Introducción

¡Bienvenido! Si te estás sumergiendo en el mundo de Aspose.Words para .NET, te espera una sorpresa. Hoy, exploraremos cómo agregar un prefijo de nombre de clase CSS al guardar un documento de Word como HTML usando Aspose.Words para .NET. Esta función es muy útil cuando desea evitar conflictos de nombres de clases en sus archivos HTML.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

-  Aspose.Words para .NET: si aún no lo ha instalado,[descarguelo aqui](https://releases.aspose.com/words/net/).
- Entorno de desarrollo: Visual Studio o cualquier otro IDE de C#.
-  Un documento de Word: usaremos un documento llamado`Rendering.docx`. Colóquelo en el directorio de su proyecto.

## Importar espacios de nombres

Primero, asegúrese de haber importado los espacios de nombres necesarios a su proyecto C#. Agregue estos en la parte superior de su archivo de código:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

¡Ahora, profundicemos en la guía paso a paso!

## Paso 1: configura tu proyecto

Antes de que podamos comenzar a agregar un prefijo de nombre de clase CSS, configuremos nuestro proyecto.

### Paso 1.1: crear un nuevo proyecto

 Encienda su Visual Studio y cree un nuevo proyecto de aplicación de consola. Nómbrelo algo pegadizo como`AsposeCssPrefixExample`.

### Paso 1.2: Agregar Aspose.Words para .NET

Si aún no lo ha hecho, agregue Aspose.Words para .NET a su proyecto a través de NuGet. Simplemente abra la consola del Administrador de paquetes NuGet y ejecute:

```bash
Install-Package Aspose.Words
```

¡Excelente! Ahora estamos listos para comenzar a codificar.

## Paso 2: cargue su documento

Lo primero que debemos hacer es cargar el documento de Word que queremos convertir a HTML.

### Paso 2.1: definir la ruta del documento

 Configure la ruta a su directorio de documentos. Por el bien de este tutorial, supongamos que su documento está en una carpeta llamada`Documents` dentro del directorio de su proyecto.

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### Paso 2.2: Cargue el documento

Ahora, carguemos el documento usando Aspose.Words:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Paso 3: configurar las opciones de guardado de HTML

A continuación, debemos configurar las opciones de guardado de HTML para incluir un prefijo de nombre de clase CSS.

### Paso 3.1: Crear opciones para guardar HTML

 Instanciar el`HtmlSaveOptions` objeto y establezca el tipo de hoja de estilo CSS en`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### Paso 3.2: Establecer el prefijo de nombre de clase CSS

 Ahora, establezcamos el`CssClassNamePrefix` propiedad al prefijo deseado. Para este ejemplo, usaremos`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## Paso 4: guarde el documento como HTML

Finalmente, guardemos el documento como un archivo HTML con nuestras opciones configuradas.


Especifique la ruta del archivo HTML de salida y guarde el documento.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## Paso 5: verificar la salida

 Después de ejecutar su proyecto, navegue hasta su`Documents` carpeta. Deberías encontrar un archivo HTML llamado`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` . Abra este archivo en un editor de texto o navegador para verificar que las clases CSS tengan el prefijo`pfx_`.

## Conclusión

¡Y ahí lo tienes! Si sigue estos pasos, habrá agregado con éxito un prefijo de nombre de clase CSS a su salida HTML usando Aspose.Words para .NET. Esta característica simple pero poderosa puede ayudarlo a mantener estilos limpios y libres de conflictos en sus documentos HTML.

## Preguntas frecuentes

### ¿Puedo usar un prefijo diferente para cada operación de guardado?
 Sí, puedes personalizar el prefijo cada vez que guardas un documento cambiando el`CssClassNamePrefix` propiedad.

### ¿Este método admite CSS en línea?
 El`CssClassNamePrefix`La propiedad funciona con CSS externo. Para CSS en línea, necesitará un enfoque diferente.

### ¿Cómo puedo incluir otras opciones para guardar HTML?
 Puede configurar varias propiedades de`HtmlSaveOptions` para personalizar su salida HTML. Comprobar el[documentación](https://reference.aspose.com/words/net/) para más detalles.

### ¿Es posible guardar el HTML en una secuencia?
 ¡Absolutamente! Puede guardar el documento en una secuencia pasando el objeto de secuencia al`Save` método.

### ¿Cómo obtengo soporte si tengo problemas?
 Puede obtener apoyo del[asponer foro](https://forum.aspose.com/c/words/8).