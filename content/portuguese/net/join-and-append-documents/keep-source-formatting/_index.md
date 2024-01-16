---
title: Mantenha a formatação original
linktitle: Mantenha a formatação original
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como anexar um documento de origem a um documento de destino preservando a formatação original usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/keep-source-formatting/
---

Este tutorial demonstra como anexar um documento de origem a um documento de destino preservando a formatação original do documento de origem usando Aspose.Words for .NET.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

-  Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo em[Aspose.Releases]https://releases.aspose.com/words/net/ ou use o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório de documentos onde os documentos de origem e destino serão salvos.

## Etapa 2: Crie os documentos de destino e de origem

 Crie instâncias de`Document` para os documentos de destino e origem.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Etapa 3: anexar o documento de origem ao documento de destino

 Use o`AppendDocument` método do documento de destino para anexar o documento de origem. Passar`ImportFormatMode.KeepSourceFormatting` como modo de formato de importação para manter a formatação original do documento de origem.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 4: salve o documento modificado

 Salve o documento modificado usando o`Save` método do`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Isso completa a implementação de anexar um documento de origem a um documento de destino, mantendo a formatação original usando Aspose.Words for .NET.

### Exemplo de código-fonte para Keep Source Formatting usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Anexe o documento de origem ao documento de destino.
	// Passe o modo de formatação para manter a formatação original do documento de origem ao importá-lo.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```