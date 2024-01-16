---
title: Junte-se à nova página
linktitle: Junte-se à nova página
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como juntar dois documentos em uma nova página preservando a formatação usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/join-new-page/
---

Este tutorial explica como juntar dois documentos em uma nova página usando Aspose.Words for .NET. O código-fonte fornecido demonstra como anexar um documento ao final de outro documento ao iniciar o documento anexado em uma nova página.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

-  Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo em[Aspose.Releases]https://releases.aspose.com/words/net/ ou use o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório de documentos onde os documentos de origem e destino estão localizados.

## Passo 2: Abra os documentos de origem e destino

 Abra os documentos de origem e destino usando o`Document` construtor de classe. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Etapa 3: configurar o início da nova seção da página

 Para iniciar o documento anexado em uma nova página, defina o`SectionStart` propriedade da primeira seção no documento de origem para`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Etapa 4: anexar o documento de origem

 Anexe o documento de origem ao documento de destino usando o`AppendDocument` método do`Document` aula. Defina o modo de formato de importação para`ImportFormatMode.KeepSourceFormatting` para preservar os estilos originais do documento de origem.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 5: salve o documento modificado

 Finalmente, salve o documento de destino modificado usando o`Save` método do`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Isso completa a implementação da união de dois documentos em uma nova página usando Aspose.Words for .NET.

### Exemplo de código-fonte para ingressar em uma nova página usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Defina o documento anexado para começar em uma nova página.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Anexe o documento de origem usando os estilos originais encontrados no documento de origem.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```