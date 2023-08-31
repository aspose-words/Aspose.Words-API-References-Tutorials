---
title: Establecer la posición de la nota al pie y la nota final
linktitle: Establecer la posición de la nota al pie y la nota final
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar la posición de las notas al pie y al final en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para establecer la posición de las notas al pie y al final en un documento de Word. Explicaremos el código fuente C# proporcionado y le mostraremos cómo implementarlo en sus propios proyectos.

 Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo ha hecho, descargue e instale la biblioteca desde[Aspose.Releases]https://releases.aspose.com/words/net/.

## Paso 1: Inicializar el objeto del documento

 Primero, inicialice el`Document` objeto proporcionando la ruta a su documento fuente:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Paso 2: Configuración de la posición de las notas al pie y al final

 A continuación, acceda al`FootnoteOptions` y`EndnoteOptions` propiedades del documento para establecer la posición de las notas al pie y al final. En este ejemplo, configuramos la posición de las notas al pie debajo del texto y la posición de las notas al final al final de la sección:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Paso 3: guardar el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

¡Eso es todo! Ha establecido con éxito la posición de las notas al pie y al final en un documento de Word utilizando Aspose.Words para .NET.

### Código fuente de ejemplo para establecer la posición de notas al pie y notas al final usando Aspose.Words para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

No dude en utilizar este código en sus propios proyectos y modificarlo según sus requisitos específicos.

### Preguntas frecuentes

#### P: ¿Cómo puedo colocar notas al pie y notas al final en Aspose.Words?

 R: Para colocar notas al pie y notas finales en Aspose.Words, debe utilizar el`FootnoteOptions` clase y el`Position` propiedad. Puede establecer esta propiedad en cualquier valor que desee, como`BottomOfPage` (al final de la página) o`EndOfSection`(al final de la sección).

#### P: ¿Es posible personalizar la posición de las notas al pie y al final de cada página o sección del documento?

R: Sí, es posible personalizar la posición de las notas al pie y al final de cada página o sección del documento. Puede utilizar los métodos de manipulación de páginas y secciones de Aspose.Words para definir posiciones específicas para notas al pie y notas al final.

#### P: ¿Cómo elimino notas al pie o notas finales de un documento?

 R: Para eliminar notas al pie o notas finales de un documento en Aspose.Words, puede utilizar métodos apropiados como`RemoveAllFootnotes` para eliminar todas las notas a pie de página o`RemoveAllEndnotes` para eliminar todas las notas finales. Asegúrese de guardar el documento después de realizar estas operaciones.

#### P: ¿Se pueden colocar las notas al pie y al final fuera de los márgenes de la página?

No, de forma predeterminada, las notas al pie y al final no se pueden colocar fuera de los márgenes de la página en Aspose.Words. Sin embargo, puede ajustar los márgenes del documento para dejar más espacio para notas al pie y notas finales si es necesario.

#### P: ¿Se pueden personalizar las notas al pie y al final con estilos de fuente o formato específicos?

R: Sí, puede personalizar las notas al pie y las notas finales con fuentes o estilos de formato específicos en Aspose.Words. Puede utilizar los métodos y propiedades disponibles para aplicar estilos de fuente, colores, tamaños de fuente, etc., notas al pie y notas al final.