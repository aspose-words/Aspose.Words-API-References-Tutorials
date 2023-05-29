---
title: Rangos Obtener texto
linktitle: Rangos Obtener texto
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda cómo extraer fácilmente texto de un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-ranges/ranges-get-text/
---

Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Entre las características que ofrece Aspose.Words está la posibilidad de obtener el texto contenido en rangos específicos de un documento. En esta guía, lo guiaremos a través de cómo usar el código fuente C# de Aspose.Words para .NET para extraer texto de un documento de Word.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una biblioteca popular que hace que trabajar con documentos de Word sea fácil y eficiente. Ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word, incluida la extracción de texto de rangos específicos.

## Cargando el documento de Word

El primer paso es cargar el documento de Word del que quieres extraer el texto. Utilice la clase Document para cargar el documento desde el archivo de origen. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

En este ejemplo, cargamos el documento "Documento.docx" ubicado en el directorio de documentos.

## Extraer texto de un rango específico

Una vez cargado el documento, puede acceder a los diferentes rangos del documento y extraer el texto deseado. En este ejemplo, extraeremos todo el texto del documento. Así es cómo:

```csharp
string text = doc.Range.Text;
```

En este ejemplo, usamos la propiedad Range de la clase Document para acceder al rango completo del documento. Luego usamos la propiedad Text para obtener el texto contenido en ese rango.

## Visualización de texto extraído

Ahora que hemos extraído el texto del rango especificado, podemos mostrarlo o procesarlo según lo necesite su aplicación. Por ejemplo, puede mostrarlo en la pantalla o guardarlo en un archivo de salida. Aquí hay un ejemplo para mostrar el texto extraído:

```csharp
Console.WriteLine(text);
```

En este ejemplo, usamos el método WriteLine de la clase Console para mostrar el texto extraído en la consola.

### Ejemplo de código fuente para la función "Obtener texto de rangos" con Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Cargue el documento de Word
Document doc = new Document(dataDir + "Document.docx");

// Extraer el texto del documento.
string text = doc.Range.Text;

// Mostrar el texto extraído
Console.WriteLine(text);
```

## Conclusión

En esta guía, hemos cubierto cómo usar Aspose.Words para .NET para extraer texto de un documento de Word usando el código fuente de C# provisto. Siguiendo los pasos proporcionados, puede extraer fácilmente texto de rangos específicos en sus documentos de Word en su aplicación C#. Aspose.Words ofrece una gran flexibilidad y potencia para trabajar con contenido de documentos, lo que le permite procesar y usar texto de acuerdo con sus necesidades específicas.