---
title: Documento de clonación
linktitle: Documento de clonación
second_title: API de procesamiento de documentos de Aspose.Words
description: Aprenda a clonar un documento de Word usando Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/clone-and-combine-documents/cloning-document/
---

En este tutorial, le diremos cómo clonar un documento de Word utilizando la función de clonación de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y crear una copia exacta de un documento existente.

## Paso 1: Cargar el documento

Para comenzar, especifique su directorio de documentos y cargue el documento existente en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Paso 2: clonar el documento

Ahora vamos a clonar el documento creando una copia exacta del mismo. Así es cómo:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### Ejemplo de código fuente para la clonación de documentos usando Aspose.Words para .NET

Aquí está el código fuente completo para la función de clonación de documentos de Aspose.Words para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

Con este código podrá clonar documentos de Word utilizando Aspose.Words para .NET. La copia exacta del documento se guardará con un nuevo nombre de archivo.

