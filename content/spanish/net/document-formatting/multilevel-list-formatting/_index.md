---
title: Formato de lista multinivel en documento de Word
linktitle: Formato de lista multinivel en documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Aprenda a crear una lista de varios niveles y aplicar formato personalizado en un documento de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/document-formatting/multilevel-list-formatting/
---
En este tutorial, le mostraremos cómo utilizar la función de formato de lista multinivel en documentos de Word con Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios.

## Paso 1: Crear y configurar el documento

Para comenzar, cree un nuevo documento y un objeto DocumentBuilder asociado. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Paso 2: formatear la lista multinivel

Ahora aplicaremos el formato de lista multinivel utilizando los métodos disponibles en el objeto DocumentBuilder. Así es cómo:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Paso 3: guardar el documento

 Después de insertar el campo del formulario de entrada de texto, guarde el documento en la ubicación deseada usando el`Save` método. Asegúrese de proporcionar la ruta de archivo adecuada:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Código fuente de ejemplo para formato de lista multinivel usando Aspose.Words para .NET

Aquí está el código fuente completo para la función de formato de listas multinivel con Aspose.Words para .NET:


```csharp

// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Con este código podrá crear una lista de varios niveles y aplicar el formato adecuado a cada nivel usando Aspose.Words para .NET.


## Conclusión

En este tutorial, hemos explorado el proceso de utilización de la función de formato de lista multinivel en un documento de Word con Aspose.Words para .NET. Si sigue los pasos descritos, puede crear listas bien organizadas con múltiples niveles, mejorando la estructura y legibilidad de sus documentos.

### Preguntas frecuentes

#### P: ¿Qué es una lista multinivel en un documento de Word?

R: Una lista multinivel en un documento de Word es una lista jerárquica que le permite organizar elementos en varios niveles de subelementos. Ayuda a presentar la información de manera estructurada, lo que facilita a los lectores la comprensión del contenido.

#### P: ¿Puedo personalizar la apariencia de la lista multinivel?

R: Sí, puedes personalizar la apariencia de la lista multinivel en tu documento de Word. Al aplicar diferentes estilos, como viñetas, números o letras, y ajustar la sangría y el espaciado, puede crear una lista organizada y visualmente atractiva.

#### P: ¿Aspose.Words para .NET admite otras opciones de formato de listas?

R: Sí, Aspose.Words para .NET proporciona un conjunto completo de funciones para formatear listas. Admite varios tipos de listas, incluidas listas con viñetas, listas numeradas y listas de varios niveles. Puede manipular el formato de las listas, agregar o eliminar elementos y personalizar su apariencia.

#### P: ¿Puedo usar Aspose.Words para .NET para trabajar con otros elementos del documento?

R: Sí, Aspose.Words para .NET ofrece amplias capacidades para trabajar con varios elementos del documento, como párrafos, tablas, imágenes y más. Le permite crear, modificar y convertir documentos de Word mediante programación, simplificando las tareas de procesamiento de documentos.