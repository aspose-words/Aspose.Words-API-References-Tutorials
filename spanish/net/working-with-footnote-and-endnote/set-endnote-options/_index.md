---
title: Establecer opciones de notas al final
linktitle: Establecer opciones de notas al final
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a configurar las opciones de notas al final en documentos de Word usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/working-with-footnote-and-endnote/set-endnote-options/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para configurar las opciones de notas finales en un documento de Word. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde el sitio web oficial.

## Paso 1: inicialización del objeto de documento

 Primero, inicialice el`Document` objeto proporcionando la ruta a su documento de origen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Paso 2: inicialización del objeto DocumentBuilder

 A continuación, inicialice el`DocumentBuilder` objeto para realizar operaciones en el documento:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: agregar texto y notas al final

 Utilizar el`Write` metodo de la`DocumentBuilder` objeto para agregar texto al documento, y el`InsertFootnote` método para insertar una nota al final:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Paso 4: Configuración de las opciones de notas al final

 Acceder al`EndnoteOptions` propiedad del documento para modificar las opciones de notas al final. En este ejemplo, configuramos la regla de reinicio para reiniciar en cada página y la posición hasta el final de la sección:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Paso 5: Guardar el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

¡Eso es todo! Ha configurado con éxito las opciones de notas finales en un documento de Word usando Aspose.Words para .NET.

### Ejemplo de código fuente para Establecer opciones de nota final usando Aspose.Words para .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Siéntase libre de usar este código en sus propios proyectos y modifíquelo de acuerdo con sus requisitos específicos.
