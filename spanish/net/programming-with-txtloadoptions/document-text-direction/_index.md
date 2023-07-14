---
title: Dirección del texto del documento
linktitle: Dirección del texto del documento
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a especificar la dirección del texto en sus documentos con Aspose.Words para .NET. Mejore la visualización de los idiomas de derecha a izquierda.
type: docs
weight: 10
url: /es/net/programming-with-txtloadoptions/document-text-direction/
---

En este tutorial, exploraremos el código fuente de C# proporcionado para la función "Dirección del texto del documento" con Aspose.Words para .NET. Esta característica le permite especificar la dirección del texto en un documento, lo cual es especialmente útil para los idiomas que se escriben de derecha a izquierda, como el hebreo o el árabe.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: configurar las opciones de carga

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 En este paso, configuramos las opciones de carga de documentos. Creamos un nuevo`TxtLoadOptions` objeto y establecer el`DocumentDirection` propiedad a`DocumentDirection.Auto`. Este valor le dice a Aspose.Words que determine automáticamente la dirección del texto según el contenido del documento.

## Paso 3: Cargar el documento

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 En este paso, cargamos el documento usando el`Document` método y pasando la ruta al archivo de texto para cargar. También utilizamos las opciones de carga especificadas.

## Paso 4: Manipule el párrafo y muestre la dirección del texto

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 En este paso, accedemos al primer párrafo del documento usando el`FirstSection` y`Body` propiedades. A continuación, accedemos a la`ParagraphFormat.Bidi` propiedad para obtener la dirección del texto del párrafo. Luego mostramos este valor en la consola.

## Paso 5: Guarde el documento

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 En este último paso, guardamos el documento resultante en formato .docx usando el`Save` y pasando la ruta al archivo de salida.

Ahora puede ejecutar el código fuente para cargar el documento de texto y determinar la dirección del texto. El documento resultante se guardará en el directorio especificado con el nombre "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Ejemplo de código fuente para la funcionalidad de dirección del texto del documento con Aspose.Words para .NET.


```csharp

            
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Conclusión

En este tutorial, exploramos la característica de dirección del texto del documento en Aspose.Words para .NET. Aprendimos a especificar la dirección del texto en un documento, especialmente para los idiomas que se escriben de derecha a izquierda, como el hebreo o el árabe.

Esta característica es esencial para garantizar que el texto se muestre correctamente en documentos multilingües. Mediante el uso de las opciones de carga adecuadas, Aspose.Words puede detectar automáticamente la dirección del texto y aplicarlo al documento.

Con Aspose.Words, puede manipular fácilmente la dirección del texto en sus documentos, brindando una experiencia de lectura fluida e intuitiva para los usuarios.

Es importante tener en cuenta que esta función es especialmente útil cuando se procesan textos con idiomas que requieren una dirección de texto específica. Aspose.Words facilita esta tarea al proporcionar herramientas poderosas para administrar la dirección del texto en sus documentos.

Recuerde usar las opciones de carga adecuadas, como configurar la dirección automática del texto, para obtener los resultados que desea en sus documentos.

Aspose.Words para .NET ofrece muchas características avanzadas para la manipulación y generación de documentos. Al explorar más a fondo la documentación y los ejemplos proporcionados por Aspose.Words, podrá aprovechar al máximo las capacidades de esta poderosa biblioteca.

Por lo tanto, no dude en integrar la dirección del texto del documento en sus proyectos Aspose.Words para .NET y aproveche sus beneficios para crear documentos multilingües atractivos y de alta calidad.