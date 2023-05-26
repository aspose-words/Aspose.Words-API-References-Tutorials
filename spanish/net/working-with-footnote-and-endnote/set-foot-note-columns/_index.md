---
title: Establecer columnas de notas al pie
linktitle: Establecer columnas de notas al pie
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a configurar el número de columnas para notas al pie en documentos de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-footnote-and-endnote/set-foot-note-columns/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para establecer la cantidad de columnas para las notas al pie en un documento de Word. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto proporcionando la ruta a su documento de origen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Paso 2: Configuración de columnas de notas al pie

 A continuación, acceda a la`FootnoteOptions`propiedad del documento y establecer la`Columns` propiedad para especificar el número de columnas para las notas al pie. En este ejemplo, lo configuramos en 3 columnas:

```csharp
doc.FootnoteOptions.Columns = 3;
```

## Paso 3: Guardar el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

¡Eso es todo! Ha establecido con éxito la cantidad de columnas para las notas al pie en un documento de Word usando Aspose.Words para .NET.

### Código fuente de ejemplo para Establecer columnas de notas al pie usando Aspose.Words para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
Document doc = new Document(dataDir + "Document.docx");

// Especifique el número de columnas con las que se formatea el área de notas al pie.
doc.FootnoteOptions.Columns = 3;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootNoteColumns.docx");
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.