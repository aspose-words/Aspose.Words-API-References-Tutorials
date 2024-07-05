---
title: Cambiar las tabulaciones de Toc en un documento de Word
linktitle: Cambiar las tabulaciones de Toc en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a cambiar las pestañas de la tabla de contenido en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Entre las funcionalidades que ofrece Aspose.Words, se encuentra la posibilidad de modificar las pestañas utilizadas en una tabla de contenidos de un documento de Word. En esta guía, le mostraremos cómo usar el código fuente C# de Aspose.Words para .NET para cambiar pestañas en la tabla de contenido de un documento.

## Comprender la biblioteca Aspose.Words

Antes de profundizar en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una biblioteca popular que hace que el procesamiento de palabras con documentos de Word sea fácil y eficiente. Ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word, incluido el cambio de pestañas de la tabla de contenido.

## Cargando el documento que contiene el índice

El primer paso es cargar el documento de Word que contiene la tabla de contenidos que desea modificar. Utilice la clase Documento para cargar el documento desde el archivo fuente. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

En este ejemplo, cargamos el documento "Tabla de contenido.docx" ubicado en el directorio de documentos.

## Cambiar pestañas en la tabla de contenido

Una vez cargado el documento, revisamos cada párrafo del documento y verificamos si está formateado usando los estilos de resultados de la Tabla de contenido (TOC). Si es así, modificamos las pestañas utilizadas para alinear los números de página. Así es cómo:

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

En este ejemplo, utilizamos un bucle para recorrer cada párrafo del documento. Luego verificamos si el párrafo tiene formato usando los estilos de resultados de la tabla de contenido (TOC). Si es así accedemos a la primera pestaña utilizada en este párrafo y la modificamos quitando la pestaña antigua y añadiendo una nueva pestaña con una posición modificada.

## Guardar documento modificado

Una vez que haya realizado los cambios necesarios en las pestañas de la tabla de contenido, puede guardar el documento modificado utilizando el método Guardar de la clase Documento. Aquí hay un ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

En este ejemplo, guardamos el documento modificado como "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Código fuente de muestra para la función "Editar pestañas de tabla de contenido" con Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento que contiene la tabla de contenidos.
Document doc = new Document(dataDir + "Table of contents.docx");

// Modificar las pestañas de la tabla de contenidos.
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

En esta guía, hemos cubierto cómo usar Aspose.Words para .NET para cambiar las pestañas en la tabla de contenido de un documento de Word usando el código fuente C# proporcionado. Si sigue los pasos proporcionados, puede personalizar fácilmente las pestañas de la tabla de contenido en sus documentos de Word en su aplicación C#. Aspose.Words ofrece una tremenda flexibilidad y potencia para trabajar con los estilos y formatos de sus documentos, permitiéndole crear documentos de Word atractivos y profesionales.

### Preguntas frecuentes para cambiar las tabulaciones del índice en un documento de Word

#### P: ¿Cuál es el propósito de la funcionalidad "Cambiar tabulaciones de índice en un documento de Word" en Aspose.Words para .NET?

R: La funcionalidad "Cambiar tabulaciones de tabla en un documento de Word" en Aspose.Words para .NET le permite modificar las tabulaciones utilizadas en la tabla de contenido de un documento de Word. Le permite personalizar la alineación y posición de los números de página y los encabezados correspondientes dentro de la tabla de contenido.

#### P: ¿Qué es Aspose.Words para .NET?

R: Aspose.Words para .NET es una potente biblioteca diseñada para el procesamiento de textos con documentos de Word en aplicaciones .NET. Proporciona funciones integrales para crear, editar, manipular y convertir documentos de Word mediante programación utilizando C# u otros lenguajes .NET.

#### P: ¿Cómo cargo un documento de Word que contiene una tabla de contenido usando Aspose.Words para .NET?

 R: Para cargar un documento de Word que contiene una tabla de contenido usando Aspose.Words para .NET, puede usar el`Document` clase y su constructor. Al proporcionar la ruta del archivo del documento, puede cargarlo en un`Document` objeto. He aquí un ejemplo:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Este fragmento de código carga el documento "Tabla de contenido.docx" ubicado en el directorio especificado.

#### P: ¿Cómo puedo cambiar las pestañas utilizadas en la tabla de contenido usando Aspose.Words para .NET?

 R: Una vez cargado el documento, puede recorrer cada párrafo del documento y comprobar si está formateado utilizando los estilos de resultados de la tabla de contenido (TOC). Si un párrafo tiene el formato de estilo TOC, puede modificar las tabulaciones utilizadas para alinear los números de página. En Aspose.Words para .NET, puede acceder al`ParagraphFormat` propiedad de cada párrafo para recuperar y modificar las tabulaciones. He aquí un ejemplo:

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

En este código, el bucle recorre cada párrafo del documento. Si un párrafo tiene un estilo TOC, accede a la primera tabulación utilizada en ese párrafo, la elimina y agrega una nueva tabulación con una posición modificada.

#### P: ¿Puedo cambiar las pestañas de varios niveles en la tabla de contenido usando Aspose.Words para .NET?

R: Sí, puede cambiar las pestañas de varios niveles en la tabla de contenido usando Aspose.Words para .NET. Al recorrer cada párrafo y verificar el estilo de la TOC, puede modificar las pestañas para cada nivel individualmente. Puede acceder al nivel deseado de la tabla de contenido y ajustar las tabulaciones en consecuencia.

#### P: ¿Cómo guardo el documento modificado después de cambiar las pestañas en la tabla de contenido usando Aspose.Words para .NET?

 R: Después de realizar los cambios necesarios en las pestañas de la tabla de contenido, puede guardar el documento modificado usando el`Save` método de la`Document` clase. Proporcione la ruta de archivo deseada y el nombre para el documento de salida como parámetro para el`Save` método. He aquí un ejemplo:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Este código guarda el documento modificado como "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### P: ¿Puedo personalizar otros aspectos de la tabla de contenido usando Aspose.Words para .NET?

R: Sí, con Aspose.Words para .NET, puede personalizar varios aspectos de la tabla de contenido. Además de cambiar las pestañas, puede modificar los estilos de fuente, el tamaño, la alineación y otras propiedades de formato de las entradas de la tabla de contenido y los números de página. Además, puede ajustar la sangría, el espaciado y el formato de los encabezados correspondientes.

#### P:. ¿Puedo cambiar la alineación de la pestaña y los caracteres principales de la tabla de contenido usando Aspose.Words para .NET?

R: Sí, puede cambiar la alineación de la pestaña y los caracteres guía de la tabla de contenido usando Aspose.Words para .NET. Al acceder a las tabulaciones y ajustar sus propiedades de alineación y líder, puede controlar la alineación y la apariencia visual de los números de página y los encabezados correspondientes en la tabla de contenido.

#### P: ¿Aspose.Words para .NET admite el cambio de otros estilos y formatos en documentos de Word?

R: Sí, Aspose.Words para .NET proporciona un amplio soporte para cambiar varios estilos y formatos en documentos de Word. Le permite modificar estilos para diferentes elementos como párrafos, encabezados, tablas, listas y más. Puede cambiar fuentes, colores, alineación, sangría, espaciado y otros aspectos de formato según sus requisitos.

#### P: ¿Puedo modificar las pestañas en la tabla de contenido de un documento de Word existente usando Aspose.Words para .NET?

R: Sí, puede modificar las pestañas en la tabla de contenido de un documento de Word existente usando Aspose.Words para .NET. Al cargar el documento, recorrer los párrafos y realizar los cambios necesarios en las tabulaciones, puede actualizar las pestañas en la tabla de contenido. Finalmente, guarde el documento para aplicar las modificaciones.