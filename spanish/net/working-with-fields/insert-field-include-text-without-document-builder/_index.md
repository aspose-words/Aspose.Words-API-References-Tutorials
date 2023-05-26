---
title: Insertar FieldIncludeText sin el Generador de documentos
linktitle: Insertar FieldIncludeText sin el Generador de documentos
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un campo FieldIncludeText en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que usa la funcionalidad "Insertar un campo FieldIncludeText" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Creando el Documento y el Párrafo

Comenzamos creando un nuevo documento e inicializando un párrafo.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Paso 3: Insertar el campo FieldIncludeText

 usamos el`AppendField()` para insertar un campo FieldIncludeText en el párrafo.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Luego configuramos las propiedades del campo FieldIncludeText especificando el nombre del marcador y el nombre del archivo fuente.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

A continuación, añadimos el párrafo al cuerpo del documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Finalmente, llamamos a la`Update()` método para actualizar el campo.

```csharp
fieldIncludeText.Update();
```

### Ejemplo del código fuente para insertar un campo FieldIncludeText con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Cree el documento y el párrafo.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Insertar campo FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

En este ejemplo, creamos un nuevo documento, inicializamos un párrafo, insertamos un FieldIncludeTexten especificando el nombre del marcador y el nombre del archivo de origen, y guardamos el documento con un nombre de archivo específico.

Esto concluye nuestra guía sobre el uso de la función "Insertar un campo incluido en el texto" con Aspose.Words para .NET.