---
title: Exportar fuentes como Base 64
linktitle: Exportar fuentes como Base 64
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a exportar fuentes como Base64 usando Aspose.Words para .NET en este tutorial detallado. Asegúrese de que las fuentes estén incrustadas y se muestren correctamente en los archivos HTML.
type: docs
weight: 10
url: /es/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---
## Introducción

Cuando se trata de manipular documentos de Word mediante programación, Aspose.Words para .NET es una potencia. Una de sus ingeniosas funciones es exportar fuentes como Base64 dentro de archivos HTML, lo que garantiza que las fuentes se incrusten y se muestren correctamente en diferentes navegadores y sistemas. En este tutorial, profundizaremos en cómo puede lograr esto. ¿Listo para hacer que las fuentes de sus documentos de Word sean compatibles con la web? ¡Empecemos!

## Requisitos previos

Antes de pasar a la codificación, asegurémonos de que tiene todo lo que necesita:

-  Aspose.Words para la biblioteca .NET: puede descargarlo desde[Lanzamientos de Aspose](https://releases.aspose.com/words/net/) página.
- Entorno de desarrollo .NET: cualquier IDE como Visual Studio funcionará perfectamente.
- Conocimientos básicos de C#: no es necesario ser un profesional, pero unos conocimientos básicos le ayudarán.

## Importar espacios de nombres

Para usar Aspose.Words para .NET, deberá importar los espacios de nombres necesarios en su código C#. Esto hace que todas las clases y métodos estén disponibles para su uso.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Paso 1: configura tu proyecto

Primero lo primero, configuremos su proyecto e instalemos la biblioteca Aspose.Words.

### 1.1 Crear un nuevo proyecto

Abra Visual Studio y cree un nuevo proyecto de aplicación de consola. Nómbralo con algo significativo como "ExportFontsBase64".

### 1.2 Instalar Aspose.Words

Puede instalar Aspose.Words para .NET a través del Administrador de paquetes NuGet:

1. Haga clic derecho en su proyecto en el Explorador de soluciones.
2. Seleccione "Administrar paquetes NuGet".
3. Busque "Aspose.Words" e instálelo.

Alternativamente, puede ejecutar el siguiente comando en la Consola del Administrador de paquetes:

```sh
Install-Package Aspose.Words
```

## Paso 2: cargue su documento de Word

Ahora que su proyecto está configurado, carguemos el documento de Word desde el que desea exportar las fuentes.

### 2.1 Definir el directorio de documentos

Primero, defina el directorio donde se encuentra su documento de Word:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Reemplazar`"YOUR DOCUMENT DIRECTORY"` con la ruta real a su directorio de documentos.

### 2.2 Cargar el documento

 A continuación, cargue su documento usando el`Document` clase:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Asegúrese de que "Rendering.docx" esté en el directorio especificado.

## Paso 3: configurar las opciones de guardado de HTML

 Para exportar fuentes como Base64, necesitamos configurar el`HtmlSaveOptions`.


 Crear una instancia de`HtmlSaveOptions` y establecer el`ExportFontsAsBase64`propiedad a`true`:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

## Paso 4: guarde el documento como HTML

Finalmente, guardemos el documento con las opciones configuradas.


 Utilice el`Save` método de la`Document` clase para guardar su documento:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Esta línea guardará su documento como un archivo HTML con fuentes exportadas como Base64, asegurando que estén incrustadas en el HTML.

## Conclusión

¡Felicidades! Ha exportado con éxito fuentes como Base64 desde un documento de Word usando Aspose.Words para .NET. Esto garantiza que sus fuentes se conserven y muestren correctamente en diferentes plataformas. Ya sea que esté preparando documentos para su visualización web o simplemente garantizando la compatibilidad, esta función es increíblemente útil.

## Preguntas frecuentes

### ¿Qué es la codificación Base64?
Base64 es un método para codificar datos binarios (como fuentes) en formato de texto. Esto garantiza la compatibilidad con formatos basados en texto como HTML.

### ¿Por qué debería utilizar Base64 para fuentes en HTML?
El uso de Base64 garantiza que las fuentes estén incrustadas directamente en el HTML, evitando problemas con archivos de fuentes faltantes y garantizando una visualización consistente.

### ¿Puedo utilizar este método para otros recursos como imágenes?
¡Absolutamente! Aspose.Words para .NET le permite incrustar varios recursos, incluidas imágenes, como Base64 en sus archivos HTML.

### ¿Qué pasa si mi documento tiene varias fuentes?
¡Ningún problema! Aspose.Words para .NET incrustará todas las fuentes utilizadas en su documento como Base64 en el archivo HTML resultante.

### ¿Aspose.Words para .NET es de uso gratuito?
 Aspose.Words para .NET es una biblioteca comercial. Sin embargo, puede descargar una versión de prueba gratuita desde[Lanzamientos de Aspose](https://releases.aspose.com/) página.
