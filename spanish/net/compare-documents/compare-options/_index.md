---
title: Comparar opciones
linktitle: Comparar opciones
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para explicar el código fuente de C# de la función Comparar opciones con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/compare-documents/compare-options/
---

En este tutorial, explicaremos cómo usar la función Comparar opciones con Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios.

## Paso 1: Compare documentos con opciones personalizadas

 Para comenzar, cargue dos documentos para comparar. En este ejemplo, utilizaremos el`Clone()` método para crear una copia del documento original. Así es cómo:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Paso 2: Configuración de las opciones de comparación

Ahora configuraremos las opciones de comparación creando un`CompareOptions` objeto y establecer las diversas propiedades según sea necesario. Así es cómo:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Paso 3: Compare documentos con opciones personalizadas

 Ahora usaremos el`Compare()` método que pasa las opciones personalizadas para comparar los dos documentos. Este método marcará los cambios en el documento original. Así es cómo:

```csharp
// Compara documentos con opciones personalizadas
docA.Compare(docB, "user", DateTime.Now, options);

// Comprobar si los documentos son iguales
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Ejemplo de código fuente para comparar opciones usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Comparar opciones con Aspose.Words para .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Con este código, puede comparar dos documentos usando opciones personalizadas para ignorar elementos específicos al comparar con Aspose.Words para .NET.

