---
title: Usar fuente de la máquina de destino
linktitle: Usar fuente de la máquina de destino
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a convertir un documento de Word a HTML fijo usando las fuentes de la máquina de destino con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Al convertir un documento de Word a HTML fijo en una aplicación de C#, es posible que desee utilizar las fuentes de la máquina de destino para asegurarse de que el HTML representado conserve el aspecto y el estilo originales del documento. Con la biblioteca Aspose.Words para .NET, puede especificar fácilmente esta funcionalidad mediante las opciones de guardado de HtmlFixedSaveOptions. En esta guía paso a paso, lo guiaremos a través de cómo usar el código fuente de C# de Aspose.Words para .NET para convertir un documento de Word a HTML fijo usando las fuentes de la máquina de destino usando HtmlFixedSaveOptions.

## Comprender la biblioteca Aspose.Words

Antes de sumergirse en el código, es importante comprender la biblioteca Aspose.Words para .NET. Aspose.Words es una poderosa biblioteca para crear, editar, convertir y proteger documentos de Word en diferentes plataformas, incluida .NET. Ofrece muchas funciones para manipular documentos, como insertar texto, cambiar el formato, agregar secciones y mucho más.

## Cargando el documento de Word

El primer paso es cargar el documento de Word que desea convertir a HTML fijo. Utilice la clase Document para cargar el documento desde el archivo de origen. Aquí hay un ejemplo :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

En este ejemplo, cargamos el documento "Viñetas con fuente alternativa.docx" ubicado en el directorio de documentos.

## Configuración de opciones de copia de seguridad

El siguiente paso es configurar las opciones de guardado para convertir a HTML fijo. Use la clase HtmlFixedSaveOptions y establezca la propiedad UseTargetMachineFonts en true para decirle a Aspose.Words que use fuentes de la máquina de destino. Aquí está cómo hacerlo:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Creamos un nuevo objeto HtmlFixedSaveOptions y establecemos la propiedad UseTargetMachineFonts en true para usar las fuentes de la máquina de destino al convertir.

## Conversión de documentos HTML fijos

Ahora que hemos configurado las opciones de guardado, podemos proceder a convertir el documento a HTML fijo. Utilice el método Guardar de la clase Documento para guardar el documento convertido en formato HTML fijo especificando las opciones de guardado. Aquí hay un ejemplo :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

En este ejemplo, guardamos el documento convertido como "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" usando las opciones de guardado especificadas.

### Ejemplo de código fuente para HtmlFixedSaveOptions con la característica "Usar fuentes de la máquina de destino" usando Aspose.Words para .NET

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cargue el documento de Word
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// Configure las opciones de copia de seguridad con la función "Usar fuentes de la máquina de destino"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Convertir documento a HTML fijo
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Conclusión

En esta guía, hemos explicado cómo convertir un documento de Word a HTML fijo usando las fuentes de la máquina de destino con la biblioteca Aspose.Words para .NET. Si sigue los pasos proporcionados y usa el código fuente de C# provisto, puede aplicar fácilmente esta funcionalidad en su aplicación de C#. La conversión a HTML fijo con las fuentes de la máquina de destino garantiza una representación fiel y consistente del documento en formato HTML.
