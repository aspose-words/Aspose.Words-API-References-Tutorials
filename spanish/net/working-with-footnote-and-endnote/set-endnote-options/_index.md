---
title: Establecer opciones de notas al final
linktitle: Establecer opciones de notas al final
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a configurar las opciones de notas al final en documentos de Word usando Aspose.Words para .NET. Tutorial paso a paso con código fuente de ejemplo.
type: docs
weight: 10
url: /es/net/working-with-footnote-and-endnote/set-endnote-options/
---

En este tutorial paso a paso, lo guiaremos sobre cómo usar Aspose.Words para .NET para configurar las opciones de notas finales en un documento de Word. Explicaremos el código fuente de C# provisto y le mostraremos cómo implementarlo en sus propios proyectos.

 Para comenzar, asegúrese de tener Aspose.Words para .NET instalado y configurado en su entorno de desarrollo. Si no lo ha hecho, descargue e instale la biblioteca desde[Aspose.Releases]https://releases.aspose.com/words/net/.

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

### Preguntas frecuentes

#### P: ¿Cómo puedo diseñar notas al final en Aspose.Words?

 R: Para diseñar notas al final en Aspose.Words, puede usar el`EndnoteOptions` clase y el`SeparatorNoteTextStyle` propiedad. Puede especificar el estilo de fuente, el tamaño, el color, etc. para las notas finales usando esta propiedad.

#### P: ¿Es posible personalizar la numeración de las notas al final de un documento?

 R: Sí, es posible personalizar la numeración de las notas al final de un documento. Puedes usar el`RestartRule` y`NumberStyle` propiedades de la`EndnoteOptions` class para definir reglas de reinicio específicas y estilos de numeración.

#### P: ¿Cómo puedo colocar las notas finales en un documento?

 R: Para colocar las notas finales en un documento, puede usar el`Position` propiedad de la`EndnoteOptions` clase. Puede especificar si las notas al final deben colocarse al final de cada página, al final de cada sección o al final del documento.

#### P: ¿Puedo personalizar el formato de numeración de las notas finales?

 R: Sí, puede personalizar el formato de la numeración de las notas finales en Aspose.Words. Utilizar el`NumberFormat` propiedad de la`EndnoteOptions` class para establecer el formato deseado, como números arábigos, números romanos, letras, etc.

#### P: ¿Es posible continuar con la numeración de notas finales entre secciones de un documento?

 R: Sí, es posible continuar con la numeración de notas al final entre las secciones de un documento. Utilizar el`RestartRule` propiedad de la`EndnoteOptions` clase y configúrelo en`RestartContinuous` para permitir que la numeración continúe entre las secciones.