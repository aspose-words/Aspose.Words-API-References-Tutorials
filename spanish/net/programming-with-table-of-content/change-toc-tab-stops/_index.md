---
title: Cambiar las paradas de tabulación de Toc en un documento de Word
linktitle: Cambiar las paradas de tabulación de Toc en un documento de Word
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a cambiar las pestañas de la tabla de contenido en un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words para .NET es una poderosa biblioteca para crear, editar y manipular documentos de Word en una aplicación C#. Entre las funcionalidades que ofrece Aspose.Words, se encuentra la posibilidad de modificar las pestañas utilizadas en una tabla de contenido de un documento de Word. En esta guía, le mostraremos cómo usar el código fuente C# de Aspose.Words para .NET para cambiar las pestañas en la tabla de contenido de un documento.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una biblioteca popular que hace que el procesamiento de textos con documentos de Word sea fácil y eficiente. Ofrece una amplia gama de funciones para crear, editar y manipular documentos de Word, incluido el cambio de pestañas de la tabla de contenido.

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

En esta guía, hemos cubierto cómo usar Aspose.Words para .NET para cambiar las pestañas en la tabla de contenido de un documento de Word usando el código fuente de C# provisto. Siguiendo los pasos proporcionados, puede personalizar fácilmente las pestañas de la tabla de contenido en sus documentos de Word en su aplicación C#. Aspose.Words ofrece una gran flexibilidad y potencia para trabajar con los estilos y el formato de sus documentos, lo que le permite crear documentos de Word atractivos y profesionales.

### Preguntas frecuentes para cambiar las paradas de tabulación de toc en un documento de Word

#### P: ¿Cuál es el propósito de la funcionalidad "Cambiar las paradas de tabulación de Toc en un documento de Word" en Aspose.Words para .NET?

R: La funcionalidad "Cambiar las paradas de tabulación en el documento de Word" en Aspose.Words para .NET le permite modificar las paradas de tabulación utilizadas en la tabla de contenido de un documento de Word. Le permite personalizar la alineación y el posicionamiento de los números de página y los títulos correspondientes dentro de la tabla de contenido.

#### P: ¿Qué es Aspose.Words para .NET?

R: Aspose.Words para .NET es una potente biblioteca diseñada para el procesamiento de textos con documentos de Word en aplicaciones .NET. Proporciona características integrales para crear, editar, manipular y convertir documentos de Word mediante programación usando C# u otros lenguajes .NET.

#### P: ¿Cómo cargo un documento de Word que contiene una tabla de contenido usando Aspose.Words para .NET?

 R: Para cargar un documento de Word que contenga una tabla de contenido usando Aspose.Words para .NET, puede usar el`Document` clase y su constructor. Al proporcionar la ruta del archivo del documento, puede cargarlo en un`Document` objeto. Aquí hay un ejemplo:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Este fragmento de código carga el documento "Tabla de contenido.docx" ubicado en el directorio especificado.

#### P: ¿Cómo puedo cambiar las pestañas utilizadas en la tabla de contenido usando Aspose.Words para .NET?

 R: Una vez que se carga el documento, puede recorrer cada párrafo del documento y verificar si está formateado usando los estilos de resultado de la Tabla de contenido (TOC). Si un párrafo tiene formato de estilo TOC, puede modificar las pestañas utilizadas para alinear los números de página. En Aspose.Words for .NET, puede acceder a la`ParagraphFormat` propiedad de cada párrafo para recuperar y modificar las tabulaciones. Aquí hay un ejemplo:

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

En este código, el ciclo itera a través de cada párrafo del documento. Si un párrafo tiene un estilo TOC, accede a la primera tabulación utilizada en ese párrafo, la elimina y agrega una nueva tabulación con una posición modificada.

#### P: ¿Puedo cambiar las pestañas de varios niveles en la tabla de contenido usando Aspose.Words para .NET?

R: Sí, puede cambiar las pestañas de varios niveles en la tabla de contenido usando Aspose.Words para .NET. Al recorrer cada párrafo y verificar el estilo de la TOC, puede modificar las pestañas para cada nivel individualmente. Puede acceder al nivel deseado de la tabla de contenido y ajustar las tabulaciones en consecuencia.

#### P: ¿Cómo guardo el documento modificado después de cambiar las pestañas en la tabla de contenido usando Aspose.Words para .NET?

 R: Después de realizar los cambios necesarios en las pestañas de la tabla de contenido, puede guardar el documento modificado utilizando el`Save` metodo de la`Document` clase. Proporcione la ruta del archivo y el nombre deseados para el documento de salida como un parámetro para el`Save` método. Aquí hay un ejemplo:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Este código guarda el documento modificado como "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### P: ¿Puedo personalizar otros aspectos de la tabla de contenido usando Aspose.Words para .NET?

R: Sí, con Aspose.Words para .NET, puede personalizar varios aspectos de la tabla de contenido. Además de cambiar las pestañas, puede modificar los estilos de fuente, el tamaño, la alineación y otras propiedades de formato de las entradas de la tabla de contenido y los números de página. Además, puede ajustar la sangría, el espaciado y el formato de los títulos correspondientes.

#### P:. ¿Puedo cambiar la alineación de las pestañas y los caracteres principales de la tabla de contenido usando Aspose.Words para .NET?

R: Sí, puede cambiar la alineación de las pestañas y los caracteres principales de la tabla de contenido mediante Aspose.Words para .NET. Al acceder a las tabulaciones y ajustar sus propiedades de alineación y guía, puede controlar la alineación y la apariencia visual de los números de página y los encabezados correspondientes en la tabla de contenido.

#### P: ¿Admite Aspose.Words para .NET cambiar otros estilos y formatos en documentos de Word?

R: Sí, Aspose.Words para .NET proporciona una amplia compatibilidad para cambiar varios estilos y formatos en documentos de Word. Te permite modificar estilos para diferentes elementos como párrafos, encabezados, tablas, listas y más. Puede cambiar las fuentes, los colores, la alineación, la sangría, el espaciado y otros aspectos de formato según sus requisitos.

#### P: ¿Puedo modificar las pestañas en la tabla de contenido de un documento de Word existente usando Aspose.Words para .NET?

R: Sí, puede modificar las pestañas en la tabla de contenido de un documento de Word existente usando Aspose.Words para .NET. Al cargar el documento, recorrer los párrafos y realizar los cambios necesarios en las tabulaciones, puede actualizar las pestañas en la tabla de contenido. Finalmente, guarde el documento para aplicar las modificaciones.