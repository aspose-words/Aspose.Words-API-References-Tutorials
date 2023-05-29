---
title: Insertar documento en la combinación de correspondencia
linktitle: Insertar documento en la combinación de correspondencia
second_title: Referencia de API de Aspose.Words para .NET
description: Aprenda a insertar un documento en otro durante la combinación de correspondencia usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/clone-and-combine-documents/insert-document-at-mail-merge/
---

En este tutorial, lo guiaremos a través de cómo insertar un documento en otro documento durante la combinación de correspondencia utilizando la función Insertar documento durante la combinación de correspondencia de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y realizar la inserción del documento.

## Paso 1: Cargar el documento principal

Para comenzar, especifique el directorio para sus documentos y cargue el documento principal en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Paso 2: configurar la combinación de correspondencia

Ahora vamos a configurar la combinación de correspondencia y especificar la devolución de llamada de combinación de campos para insertar un documento en otro documento. Así es cómo:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Paso 3: ejecutar la combinación de correspondencia

Ejecutaremos la combinación de correspondencia proporcionando los nombres de los campos de combinación y los datos correspondientes. Así es cómo:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Ejemplo de código fuente para Insertar documento en la combinación de correspondencia usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Insertar documento en combinación de correspondencia de Aspose.Words para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
//El documento principal tiene un campo de combinación llamado "Documento_1".
// Los datos correspondientes para este campo contienen una ruta completa al documento.
// Eso debe ser insertado en este campo.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Con este código podrá insertar un documento en otro documento durante la combinación de correspondencia utilizando Aspose.Words para .NET. El documento resultante se guardará con un nuevo nombre.



