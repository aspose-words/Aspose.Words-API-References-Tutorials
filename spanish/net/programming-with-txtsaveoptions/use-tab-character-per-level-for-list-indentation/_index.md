---
title: Use el carácter de tabulación por nivel para la sangría de la lista
linktitle: Use el carácter de tabulación por nivel para la sangría de la lista
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a usar las listas de sangría con la función de caracteres de tabulación en Aspose.Words para .NET. Ahorre tiempo y mejore su flujo de trabajo con esta potente función.
type: docs
weight: 10
url: /es/net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

En este tutorial, exploraremos el código fuente de C# provisto para la función "Usar un carácter de tabulación por nivel para la sangría de la lista" con Aspose.Words para .NET. Esta función le permite aplicar tabulaciones para sangrar listas en cada nivel, lo que brinda mayor flexibilidad y control sobre la apariencia de sus documentos.

## Paso 1: Configuración del entorno

Antes de comenzar, asegúrese de haber configurado su entorno de desarrollo con Aspose.Words para .NET. Asegúrese de haber agregado las referencias necesarias e importado los espacios de nombres apropiados.

## Paso 2: Crear el documento y el generador

```csharp
// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 En este paso, creamos un nuevo`Document` objeto y un asociado`DocumentBuilder` objeto. Estos objetos nos permitirán manipular y generar nuestro documento.

## Paso 3: crear una lista con tres niveles de sangría

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

 En este paso, aplicamos el formato predeterminado de los números de lista usando el`ApplyNumberDefault()` método del formateador de listas. Luego, agregamos tres elementos a nuestra lista usando el generador de documentos`Writeln()` y`Write()` métodos. usamos el`ListIndent()` método para incrementar la sangría en cada nivel.

## Paso 4: Configure las opciones de grabación

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

 En este paso configuramos las opciones para guardar el documento. Creamos un nuevo`TxtSaveOptions` objeto y establecer el`ListIndentation.Count`propiedad a 1 para especificar el número de caracteres de tabulación por nivel de sangría. También configuramos el`ListIndentation.Character` propiedad a '\t' para especificar que queremos usar caracteres de tabulación.

## Paso 5: Guarde el documento

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

 En este último paso, guardamos el documento con las opciones de guardado especificadas. usamos el`Save()` método del documento pasando la ruta completa del archivo de salida y las opciones de guardado.


Ahora puede ejecutar el código fuente para generar un documento con sangría de lista usando caracteres de tabulación. El archivo de salida se guardará en el directorio especificado con el nombre "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt".

### Fuente de código de ejemplo para la función Usar un carácter de tabulación por nivel para la sangría de lista con Aspose.Words para .NET:

```csharp

// Ruta a su directorio de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crear una lista con tres niveles de sangría
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");

TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);

```

Ahora que ha terminado de generar su documento con sangría de lista usando caracteres de tabulación, puede usar Markdown para formatear el contenido de su artículo. Asegúrese de usar etiquetas de formato adecuadas para resaltar títulos, subtítulos y el código fuente incluido.