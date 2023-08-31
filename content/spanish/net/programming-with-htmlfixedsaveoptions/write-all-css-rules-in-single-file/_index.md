---
title: Escriba todas las reglas CSS en un solo archivo
linktitle: Escriba todas las reglas CSS en un solo archivo
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda cómo convertir un documento de Word a HTML fijo escribiendo todas las reglas CSS en un solo archivo con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Al convertir un documento de Word a HTML fijo en una aplicación C#, es posible que desee consolidar todas las reglas CSS en un solo archivo para una mejor organización y portabilidad. Con la biblioteca Aspose.Words para .NET, puede especificar fácilmente esta funcionalidad utilizando las opciones de guardado de HtmlFixedSaveOptions. En esta guía paso a paso, le explicaremos cómo utilizar Aspose.Words para el código fuente .NET C# para convertir un documento de Word a HTML fijo escribiendo todas las reglas CSS en un solo archivo usando las opciones de guardado HtmlFixedSaveOptions.

## Comprender la biblioteca Aspose.Words

Antes de profundizar en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluido .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar formato, agregar secciones y mucho más.

## Cargando el documento de Word

El primer paso es cargar el documento de Word que desea convertir a HTML fijo. Utilice la clase Documento para cargar el documento desde el archivo fuente. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

En este ejemplo, cargamos el documento "Document.docx" ubicado en el directorio de documentos.

## Configurar opciones de copia de seguridad

El siguiente paso es configurar las opciones de guardado para convertir a HTML fijo. Utilice la clase HtmlFixedSaveOptions y establezca la propiedad SaveFontFaceCssSeparately en falso para escribir todas las reglas CSS en un solo archivo. He aquí cómo hacerlo:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Creamos un nuevo objeto HtmlFixedSaveOptions y configuramos la propiedad SaveFontFaceCssSeparately en falso para escribir todas las reglas CSS en un solo archivo.

## Conversión de documentos HTML fija

Ahora que hemos configurado las opciones de guardar, podemos proceder a convertir el documento a HTML fijo. Utilice el método Guardar de la clase Documento para guardar el documento convertido en formato HTML fijo especificando opciones de guardado. Aquí hay un ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

En este ejemplo, guardamos el documento convertido como "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" usando las opciones de guardado especificadas.

### Código fuente de ejemplo para HtmlFixedSaveOptions con la función "Escribir todas las reglas CSS en un archivo" usando Aspose.Words para .NET

```csharp
// Ruta de acceso a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargar el documento de Word
Document doc = new Document(dataDir + "Document.docx");

// Configure las opciones de copia de seguridad con la función "Escribir todas las reglas CSS en un archivo"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Convertir documento a HTML fijo
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Conclusión

En esta guía, cubrimos cómo convertir un documento de Word a HTML fijo escribiendo todas las reglas CSS en un solo archivo usando HtmlFixedSaveOptions con la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y utiliza el código fuente de C# proporcionado, puede aplicar fácilmente esta funcionalidad en su aplicación C#. Escribir todas las reglas CSS en un solo archivo facilita la organización y administración del código HTML generado durante la conversión del documento.