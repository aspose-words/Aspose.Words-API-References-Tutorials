---
title: Insertar ASKField sin Document Builder
linktitle: Insertar ASKField sin Document Builder
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un campo ASK en sus documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Aquí hay una guía paso a paso para explicar el código fuente de C# a continuación, que usa la función "Insertar un campo ASK sin DocumentBuilder" de Aspose.Words para .NET. Asegúrese de seguir cada paso cuidadosamente para obtener los resultados deseados.

## Paso 1: Configuración del directorio de documentos

En el código provisto, debe especificar el directorio de sus documentos. Reemplace el valor "SU DIRECTORIO DE DOCUMENTOS" con la ruta adecuada a su directorio de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Paso 2: Creando el Documento y el Párrafo

Comenzamos creando un nuevo documento y recuperando el primer párrafo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Paso 3: Inserción del campo ASK

 usamos el`AppendField()` para insertar un campo ASK en el párrafo.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Luego configuramos las diversas propiedades del campo ASK especificando los valores deseados.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Finalmente, llamamos a la`Update()` método para actualizar el campo.

```csharp
field. Update();
```

### Ejemplo del código fuente para insertar un campo ASK sin DocumentBuilder con Aspose.Words para .NET

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creación de documentos.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Inserte el campo ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

En este ejemplo, creamos un nuevo documento, insertamos un campo ASK sin usar DocumentBuilder, configuramos las diversas propiedades del campo y guardamos el documento con un nombre de archivo específico.

Esto concluye nuestra guía sobre el uso de la función "Insertar campo ASK sin DocumentBuilder" con Aspose.Words para .NET.