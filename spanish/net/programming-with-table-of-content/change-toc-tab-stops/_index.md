---
title: Cambiar paradas de tabulación de índice
linktitle: Cambiar paradas de tabulación de índice
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a cambiar las pestañas de la tabla de contenido en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Entre las funcionalidades que ofrece Aspose.Words, se encuentra la posibilidad de modificar las pestañas utilizadas en una tabla de contenido de un documento de Word. En esta guía, le mostraremos cómo usar el código fuente C# de Aspose.Words para .NET para cambiar las pestañas en la tabla de contenido de un documento.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una biblioteca popular que hace que trabajar con documentos de Word sea fácil y eficiente. Ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word, incluido el cambio de pestañas de la tabla de contenido.

## Cargar el documento que contiene la tabla de contenido

El primer paso es cargar el documento de Word que contiene la tabla de contenido que desea modificar. Utilice la clase Document para cargar el documento desde el archivo de origen. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

En este ejemplo, cargamos el documento "Tabla de contenido.docx" ubicado en el directorio de documentos.

## Cambio de pestañas en la tabla de contenido

Una vez que se carga el documento, revisamos cada párrafo del documento y verificamos si está formateado usando los estilos de resultados de la Tabla de contenido (TOC). Si es así, modificamos las pestañas utilizadas para alinear los números de página. Así es cómo:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

En este ejemplo, estamos usando un bucle para recorrer cada párrafo del documento. Luego verificamos si el párrafo está formateado usando los estilos de resultados de la tabla de contenido (TOC). Si es así, accedemos a la primera pestaña utilizada en este párrafo y la modificamos eliminando la pestaña anterior y agregando una nueva pestaña con una posición modificada.

## Guardar documento modificado

Una vez que haya realizado los cambios necesarios en las pestañas de la tabla de contenido, puede guardar el documento modificado utilizando el método Guardar de la clase Documento. Aquí hay un ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

En este ejemplo, guardamos el documento modificado como "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Ejemplo de código fuente para la función "Editar pestañas de tabla de contenido" con Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento que contiene la tabla de contenido
Document doc = new Document(dataDir + "Table of contents.docx");

// Modificar las pestañas de la tabla de contenidos
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Guardar el documento modificado
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Conclusión

En esta guía, hemos cubierto cómo usar Aspose.Words para .NET para cambiar las pestañas en la tabla de contenido de un documento de Word usando el código fuente de C# proporcionado. Siguiendo los pasos proporcionados, puede personalizar fácilmente las pestañas de la tabla de contenido en sus documentos de Word en su aplicación C#. Aspose.Words ofrece una gran flexibilidad y potencia para trabajar con los estilos y el formato de sus documentos, lo que le permite crear documentos de Word atractivos y profesionales.