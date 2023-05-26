---
title: Cambiar el estilo del nivel de TOC
linktitle: Cambiar el estilo del nivel de TOC
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a cambiar fácilmente el estilo de un nivel de tabla de contenido en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-of-content/change-style-of-toc-level/
---

Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Entre las características que ofrece Aspose.Words está la posibilidad de cambiar el estilo de un nivel específico de la tabla de contenido de un documento. En esta guía, le mostraremos cómo usar el código fuente C# de Aspose.Words para .NET para cambiar el estilo de un nivel de la tabla de contenido de un documento de Word.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una biblioteca popular que hace que trabajar con documentos de Word sea fácil y eficiente. Ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word, incluido el cambio de estilo de la tabla de contenido.

## Creando un nuevo documento

El primer paso es crear un nuevo documento de Word en el que desee cambiar el estilo de la tabla de contenido. Use la clase Document para crear un nuevo documento. Aquí hay un ejemplo :

```csharp
Document doc = new Document();
```

En este ejemplo, estamos creando un nuevo documento vacío.

## Cambiar el estilo de un nivel de tabla de contenido

Una vez que se crea el documento, puede acceder a los estilos del documento y cambiar el estilo utilizado para un nivel específico de la tabla de contenido. En este ejemplo, modificaremos el estilo utilizado para el primer nivel de la tabla de contenido. Así es cómo:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

En este ejemplo, usamos la propiedad Styles de la clase Document para acceder a los estilos de documentos. A continuación, usamos el identificador de estilo StyleIdentifier.Toc1 para acceder al estilo utilizado para el primer nivel de la tabla de contenido. Finalmente, modificamos la propiedad Font.Bold del estilo para ponerlo en negrita.

## Guardar documento modificado

Una vez que haya realizado las modificaciones necesarias en el estilo de la tabla de contenido, puede guardar el documento modificado utilizando el método Guardar de la clase Documento. Aquí hay un ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

En este ejemplo, guardamos el documento modificado como "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

## Ejemplo de código fuente para la función "Cambiar el estilo de un nivel de tabla de contenido" con Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crear un nuevo documento
Document doc = new Document();

// Modificación del estilo del primer nivel de la tabla de contenido
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

// Guardar el documento modificado
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## Conclusión

En esta guía, explicamos cómo usar Aspose.Words para .NET para cambiar el estilo de un nivel de la tabla de contenido de un documento de Word usando el código fuente de C# proporcionado. Siguiendo los pasos proporcionados, puede personalizar fácilmente el estilo de la tabla de contenido en sus documentos de Word en su aplicación C#. Aspose.Words ofrece una gran flexibilidad y potencia para trabajar con los estilos y el formato de sus documentos, lo que le permite crear documentos de Word atractivos y profesionales.