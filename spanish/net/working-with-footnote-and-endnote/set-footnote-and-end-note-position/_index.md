---
title: Establecer la posición de la nota al pie y la nota final
linktitle: Establecer la posición de la nota al pie y la nota final
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a establecer la posición de las notas al pie y al final en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para establecer la posición de las notas al pie y al final en un documento de Word. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto proporcionando la ruta a su documento de origen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Paso 2: Configuración de la posición de la nota al pie y la nota al final

 A continuación, acceda a la`FootnoteOptions` y`EndnoteOptions`propiedades del documento para establecer la posición de las notas al pie y al final. En este ejemplo, configuramos la posición de las notas al pie para que estén debajo del texto y la posición de las notas al final para que estén al final de la sección:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Paso 3: Guardar el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

¡Eso es todo! Ha establecido con éxito la posición de las notas al pie y las notas al final en un documento de Word usando Aspose.Words para .NET.

### Código fuente de ejemplo para establecer la posición de la nota al pie y la nota al final usando Aspose.Words para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.
