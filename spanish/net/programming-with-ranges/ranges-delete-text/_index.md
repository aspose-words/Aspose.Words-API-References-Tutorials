---
title: Rangos Borrar texto
linktitle: Rangos Borrar texto
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a eliminar texto en rangos específicos en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-ranges/ranges-delete-text/
---

Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Entre las funciones que ofrece Aspose.Words se encuentra la capacidad de eliminar texto específico dentro de rangos definidos de un documento. En esta guía, lo guiaremos a través de cómo usar el código fuente C# de Aspose.Words para .NET para eliminar texto en rangos específicos en un documento de Word.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una biblioteca popular que hace que trabajar con documentos de Word sea fácil y eficiente. Ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word, incluida la eliminación de texto en rangos específicos.

## Cargando el documento de Word

El primer paso es cargar el documento de Word donde desea eliminar el texto. Utilice la clase Document para cargar el documento desde el archivo de origen. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

En este ejemplo, cargamos el documento "Documento.docx" ubicado en el directorio de documentos.

## Eliminar texto en rangos específicos

Una vez que se carga el documento, puede navegar a las secciones del documento y especificar los rangos donde desea eliminar el texto. En este ejemplo, eliminaremos todo el texto de la primera sección del documento. Así es cómo:

```csharp
doc.Sections[0].Range.Delete();
```

En este ejemplo, estamos accediendo a la primera sección del documento utilizando el índice 0 (las secciones se indexan desde 0). A continuación, llamamos al método Eliminar en el rango de la sección para eliminar todo el texto de ese rango.

## Guardar documento modificado

Una vez que haya eliminado el texto en los rangos especificados, puede guardar el documento modificado utilizando el método Guardar de la clase Documento. Aquí hay un ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithRangesDeleteText.ModifiedDocument.docx");
```

En este ejemplo, guardamos el documento modificado como "WorkingWithRangesDeleteText.ModifiedDocument.docx".

### Ejemplo de código fuente para la funcionalidad "Eliminar texto en rangos" con Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Cargue el documento de Word
Document doc = new Document(dataDir + "Document.docx");

// Eliminar el texto en la primera sección del documento
doc.Sections[0].Range.Delete();

// Guardar el documento modificado
doc.Save(dataDir + "WorkingWithRangesDeleteText.ModifiedDocument.docx");
```

## Conclusión

En esta guía, hemos cubierto cómo usar Aspose.Words para .NET para eliminar texto en rangos específicos de un documento de Word usando el código fuente de C# proporcionado. Siguiendo los pasos proporcionados, puede eliminar fácilmente texto en rangos definidos en sus documentos de Word en su aplicación C#. Aspose.Words ofrece una gran flexibilidad y potencia para trabajar con rangos de texto, lo que le permite crear y editar documentos de Word con precisión y propósito.