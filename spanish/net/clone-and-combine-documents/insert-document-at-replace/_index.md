---
title: Insertar documento en reemplazar
linktitle: Insertar documento en reemplazar
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a insertar un documento en reemplazo usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/clone-and-combine-documents/insert-document-at-replace/
---

En este tutorial, lo guiaremos a través de cómo insertar un documento en otro documento al reemplazarlo usando la función Insertar documento al reemplazar de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y realizar la inserción del documento.

## Paso 1: Cargar el documento principal

Para comenzar, especifique el directorio para sus documentos y cargue el documento principal en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Paso 2: configurar las opciones de búsqueda y reemplazo

Ahora configuraremos las opciones de buscar y reemplazar especificando la dirección de búsqueda y la devolución de llamada de reemplazo para insertar un documento en otro documento. Así es cómo:

```csharp
// Configura las opciones de búsqueda y reemplazo.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Paso 3: llamar al método de reemplazo

Ahora llamaremos al método replace para buscar y reemplazar el texto especificado con una cadena vacía, usando las opciones configuradas. Así es cómo:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Ejemplo de código fuente para Insertar documento en reemplazo usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Insertar documento al reemplazar Aspose.Words para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Establecer opciones de buscar y reemplazar.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Llame al método de reemplazo.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```