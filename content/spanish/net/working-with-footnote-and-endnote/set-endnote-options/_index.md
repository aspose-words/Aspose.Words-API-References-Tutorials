---
title: Establecer opciones de notas finales
linktitle: Establecer opciones de notas finales
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a configurar opciones de notas finales en documentos de Word usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/working-with-footnote-and-endnote/set-endnote-options/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para configurar opciones de notas finales en un documento de Word. Explicaremos el código fuente C# proporcionado y le mostraremos cómo implementarlo en sus propios proyectos.

 Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si aún no lo ha hecho, descargue e instale la biblioteca desde[Aspose.Releases]https://releases.aspose.com/words/net/.

## Paso 1: Inicializar el objeto del documento

 Primero, inicialice el`Document` objeto proporcionando la ruta a su documento fuente:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Paso 2: inicializando el objeto DocumentBuilder

 A continuación, inicialice el`DocumentBuilder` objeto para realizar operaciones en el documento:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 3: agregar texto y nota final

 Utilizar el`Write` método de la`DocumentBuilder` objeto para agregar texto al documento, y el`InsertFootnote` método para insertar una nota al final:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Paso 4: configurar las opciones de las notas finales

 Acceder al`EndnoteOptions` Propiedad del documento para modificar las opciones de las notas finales. En este ejemplo, configuramos la regla de reinicio para reiniciar en cada página y la posición al final de la sección:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Paso 5: guardar el documento

Finalmente, guarde el documento modificado:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

¡Eso es todo! Ha configurado correctamente las opciones de notas finales en un documento de Word utilizando Aspose.Words para .NET.

### Código fuente de ejemplo para establecer opciones de notas finales usando Aspose.Words para .NET

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

No dude en utilizar este código en sus propios proyectos y modificarlo según sus requisitos específicos.

### Preguntas frecuentes

#### P: ¿Cómo puedo aplicar estilo a las notas finales en Aspose.Words?

R: Para aplicar estilo a las notas finales en Aspose.Words, puede utilizar el`EndnoteOptions` clase y el`SeparatorNoteTextStyle` propiedad. Puede especificar el estilo, tamaño, color, etc. de fuente para las notas finales utilizando esta propiedad.

#### P: ¿Es posible personalizar la numeración de las notas finales en un documento?

 R: Sí, es posible personalizar la numeración de las notas finales de un documento. Puedes usar el`RestartRule` y`NumberStyle` propiedades de la`EndnoteOptions` clase para definir reglas de reinicio específicas y estilos de numeración.

#### P: ¿Cómo puedo colocar notas al final en un documento?

 R: Para colocar notas finales en un documento, puede utilizar el`Position` propiedad de la`EndnoteOptions` clase. Puede especificar si las notas finales deben colocarse al final de cada página, al final de cada sección o al final del documento.

#### P: ¿Puedo personalizar el formato de numeración de las notas al final?

 R: Sí, puede personalizar el formato de numeración de notas al final en Aspose.Words. Utilizar el`NumberFormat` propiedad de la`EndnoteOptions` class para establecer el formato deseado, como números arábigos, números romanos, letras, etc.

#### P: ¿Es posible continuar con la numeración de notas al final entre secciones de un documento?

R: Sí, es posible continuar con la numeración de notas al final entre secciones de un documento. Utilizar el`RestartRule` propiedad de la`EndnoteOptions` clase y configúrelo en`RestartContinuous` para permitir que la numeración continúe entre secciones.