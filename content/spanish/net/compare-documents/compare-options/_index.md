---
title: Comparar opciones en un documento de Word
linktitle: Comparar opciones en un documento de Word
second_title: API de procesamiento de documentos Aspose.Words
description: Guía paso a paso para explicar el código fuente de C# de la función Comparar opciones en documentos de Word con Aspose.Words para .NET.
type: docs
weight: 10
url: /es/net/compare-documents/compare-options/
---
En este tutorial, explicaremos cómo utilizar la función Comparar opciones en documentos de Word con Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y aplicar los cambios.

## Paso 1: comparar documentos con opciones personalizadas

 Para comenzar, cargue dos documentos para comparar. En este ejemplo, usaremos el`Clone()` método para crear una copia del documento original. Así es cómo:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Paso 2: configurar opciones de comparación

 Ahora configuraremos las opciones de comparación creando un`CompareOptions` objeto y estableciendo las diversas propiedades según sea necesario. Así es cómo:

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

## Paso 3: comparar documentos con opciones personalizadas

 Ahora usaremos el`Compare()` método que pasa las opciones personalizadas para comparar los dos documentos. Este método marcará los cambios en el documento original. Así es cómo:

```csharp
// Compare documentos con opciones personalizadas
docA.Compare(docB, "user", DateTime.Now, options);

// Comprueba si los documentos son iguales.
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Código fuente de ejemplo para comparar opciones usando Aspose.Words para .NET

Aquí está el código fuente completo de la función Comparar opciones con Aspose.Words para .NET:

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

Con este código puede comparar dos documentos usando opciones personalizadas para ignorar elementos específicos al comparar con Aspose.Words para .NET.

## Conclusión

En este tutorial, aprendimos cómo usar las opciones de comparación en Aspose.Words para .NET para personalizar el proceso de comparación al comparar dos documentos. Al especificar diferentes opciones, puede ignorar elementos específicos y hacer que el proceso de comparación sea más flexible. Esta característica le permite tener un mayor control sobre el proceso de comparación, adaptándolo a sus requisitos específicos. Aspose.Words para .NET proporciona potentes capacidades de comparación de documentos, lo que facilita la identificación de diferencias entre documentos ignorando ciertos elementos según sea necesario.

### Preguntas frecuentes

#### P: ¿Cuál es el propósito de utilizar las opciones de comparación en Aspose.Words para .NET?

R: Las opciones de comparación en Aspose.Words para .NET le permiten personalizar el proceso de comparación al comparar dos documentos. Con estas opciones, puede especificar qué elementos ignorar durante la comparación, como cambios de formato, encabezados y pies de página, tablas, campos, comentarios, cuadros de texto y notas al pie.

#### P: ¿Cómo uso las opciones de comparación en Aspose.Words para .NET?

R: Para usar las opciones de comparación en Aspose.Words para .NET, siga estos pasos:
1. Cargue los dos documentos que desea comparar en objetos de documento separados.
2.  Utilizar el`Clone()` método para crear una copia del documento original.
3.  Crear un`CompareOptions` objeto y establecer sus propiedades para personalizar el proceso de comparación. Puede especificar qué elementos ignorar durante la comparación.
4.  Utilizar el`Compare()` método en uno de los documentos y pasar el otro documento y el`CompareOptions` objeto como parámetros. Este método comparará los documentos según las opciones especificadas y marcará los cambios en el documento original.
5.  Comprobar el`Revisions` propiedad del documento original. Si el recuento es cero, significa que los documentos son idénticos, considerando las opciones especificadas.

#### P: ¿Cuáles son las opciones comunes disponibles en CompareOptions?

R: Las opciones comunes disponibles en CompareOptions incluyen:
- `IgnoreFormatting`: Ignora los cambios de formato.
- `IgnoreHeadersAndFooters`: Ignora los cambios en encabezados y pies de página.
- `IgnoreCaseChanges`: Ignora los cambios de mayúsculas y minúsculas (mayúsculas/minúsculas).
- `IgnoreTables`: Ignora los cambios en las tablas.
- `IgnoreFields`: Ignora los cambios en los campos.
- `IgnoreComments`: Ignora los cambios en los comentarios.
- `IgnoreTextboxes`Ignora los cambios en los cuadros de texto.
- `IgnoreFootnotes`: Ignora los cambios en las notas al pie.

#### P: ¿Puedo utilizar opciones personalizadas para elementos específicos durante la comparación de documentos?

 R: Sí, puede utilizar opciones personalizadas para elementos específicos durante la comparación de documentos. Al establecer las propiedades del`CompareOptions` objeto en consecuencia, puede elegir qué elementos ignorar y cuáles considerar durante la comparación.