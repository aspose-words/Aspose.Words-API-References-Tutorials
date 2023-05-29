---
title: Por páginas
linktitle: Por páginas
second_title: Referencia de API de Aspose.Words para .NET
description: Guía paso a paso para explicar el código fuente de C# de la función Página por página de Aspose.Words para .NET
type: docs
weight: 10
url: /es/net/split-document/page-by-page/
---

En este tutorial, lo guiaremos a través de cómo dividir un documento de Word en páginas individuales utilizando la función Página por página de Aspose.Words para .NET. Siga los pasos a continuación para comprender el código fuente y obtener documentos separados para cada página.

## Paso 1: Cargar el documento

Para comenzar, especifique el directorio de su documento y cárguelo en un objeto Documento. Así es cómo:

```csharp
// Ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Paso 2: Divide el documento por página

Ahora iteraremos a través de cada página del documento y dividiremos el documento en páginas individuales. Así es cómo:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Guarde cada página como un documento separado.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

## Paso 3: Combinar documentos

Una vez que tenga documentos separados para cada página, puede fusionarlos si es necesario. Así es cómo:

```csharp
MergeDocuments();
```

### Ejemplo de código fuente para página por página usando Aspose.Words para .NET

Aquí está el código fuente completo para la función Página por página de Aspose.Words para .NET:

```csharp
// La ruta al directorio de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Guarde cada página como un documento separado.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


MergeDocuments();
```

Con este código podrá dividir un documento de Word en páginas individuales usando Aspose.Words para .NET. También puede fusionar documentos separados si es necesario.

