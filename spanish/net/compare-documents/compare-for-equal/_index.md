---
title: Comparar por igual
linktitle: Comparar por igual
second_title: API de procesamiento de documentos de Aspose.Words
description: Guía paso a paso para explicar el código fuente de C# de la función Compare for Equals con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/compare-documents/compare-for-equal/
---

En este tutorial, lo guiaremos a través de cómo usar la función Comparar para iguales con Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios.

## Paso 1: Comparación de documentos

 Para comenzar, cargue dos documentos para comparar. En este ejemplo, utilizaremos el`Clone()` método para crear una copia del documento original. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## Paso 2: Comparación de documentos

 Ahora usaremos el`Compare()` método para comparar los dos documentos. Este método marcará los cambios en el documento original. Así es cómo:

```csharp
// Compara los documentos
docA.Compare(docB, "user", DateTime.Now);

// Comprobar si los documentos son iguales
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### Ejemplo de código fuente para Compare For Equal usando Aspose.Words para .NET

Aquí está el código fuente completo para la característica Compare for Equals con Aspose.Words para .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA ahora contiene cambios como revisiones.
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Con este código, podrá comparar dos documentos y determinar si son iguales usando Aspose.Words para .NET.

