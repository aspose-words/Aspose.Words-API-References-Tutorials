---
title: Insertar documento en la combinación de correspondencia
linktitle: Insertar documento en la combinación de correspondencia
second_title: API de procesamiento de documentos de Aspose.Words
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
// El documento principal tiene un campo de combinación llamado "Documento_1".
// Los datos correspondientes para este campo contienen una ruta completa al documento.
// Eso debe ser insertado en este campo.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Con este código podrá insertar un documento en otro documento durante la combinación de correspondencia utilizando Aspose.Words para .NET. El documento resultante se guardará con un nuevo nombre.


## Conclusión

En este tutorial, exploramos cómo insertar un documento en otro documento durante la combinación de correspondencia mediante la función Insertar documento durante la combinación de correspondencia de Aspose.Words para .NET. Al configurar la combinación de correspondencia y proporcionar los datos necesarios, puede ensamblar documentos dinámicamente al combinar varias plantillas o secciones de documentos. Aspose.Words para .NET proporciona una manera flexible y poderosa de administrar escenarios complejos de generación de documentos, lo que la convierte en una herramienta valiosa para automatizar las tareas de creación y manipulación de documentos.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de insertar un documento en otro documento durante la combinación de correspondencia?

R: Insertar un documento en otro documento durante la combinación de correspondencia le permite combinar diferentes plantillas o secciones de documentos de forma dinámica en función de los datos proporcionados durante el proceso de combinación. Esta característica es particularmente útil cuando desea ensamblar documentos complejos fusionando varias plantillas o secciones predefinidas en un documento final.

#### P: ¿Cómo inserto un documento en otro documento durante la combinación de correspondencia usando Aspose.Words para .NET?

R: Para insertar un documento en otro documento durante la combinación de correspondencia usando Aspose.Words para .NET, siga estos pasos:
1. Cargue el documento principal que servirá como base en un objeto Documento.
2. Configure la combinación de correspondencia y especifique la devolución de llamada de combinación de campos para manejar la inserción de documentos.
3. Ejecute la combinación de correo con los nombres de los campos de combinación y los datos correspondientes (ruta al documento que se insertará).

#### P: ¿Cómo puedo personalizar el comportamiento de inserción durante la combinación de correspondencia?

R: Para personalizar el comportamiento de inserción durante la combinación de correspondencia, puede implementar un FieldMergingCallback personalizado heredándolo de la interfaz IFieldMergingCallback. Esto le permite controlar cómo se insertan y combinan los documentos según sus requisitos específicos.

#### P: ¿Puedo insertar varios documentos durante la combinación de correspondencia?

R: Sí, puede insertar varios documentos durante la combinación de correspondencia proporcionando los datos adecuados para cada campo de combinación. Para cada campo de combinación que requiera la inserción de un documento, especifique la ruta al documento correspondiente como datos.


