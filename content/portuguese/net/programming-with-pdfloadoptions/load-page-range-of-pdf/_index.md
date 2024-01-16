---
title: Carregar intervalo de páginas do PDF
linktitle: Carregar intervalo de páginas do PDF
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para carregar um intervalo específico de páginas PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

Neste tutorial, orientaremos você sobre como carregar um intervalo de páginas específico de um documento PDF usando Aspose.Words for .NET. Siga os passos abaixo:

## Passo 1: Carregando uma série de páginas PDF

Use o código a seguir para carregar um intervalo de páginas específico de um documento PDF:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 Neste exemplo, estamos carregando a primeira página do documento PDF. Você pode alterar os valores de`PageIndex` e`PageCount` para o intervalo de páginas desejado.

## Passo 2: Salvando o documento

 Finalmente, você pode salvar o documento contendo o intervalo de páginas específico usando o`Save` método:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Certifique-se de especificar o caminho correto para salvar o documento editado.

Isso é tudo ! Agora você carregou um intervalo de páginas específico de um documento PDF usando Aspose.Words for .NET.

### Exemplo de código-fonte para carregar intervalo de páginas de PDF usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Lembre-se de especificar o caminho correto para o diretório dos seus documentos PDF.



