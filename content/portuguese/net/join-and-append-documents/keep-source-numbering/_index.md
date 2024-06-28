---
title: Mantenha a numeração da fonte
linktitle: Mantenha a numeração da fonte
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como anexar um documento preservando a formatação da numeração de origem no Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/keep-source-numbering/
---

Este tutorial explica como anexar um documento de origem a um documento de destino, preservando a formatação de numeração original dos parágrafos numerados usando Aspose.Words for .NET.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

-  Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo em[Aspose.Releases]https://releases.aspose.com/words/net/ ou use o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório de documentos onde os documentos de origem e destino serão salvos.

## Etapa 2: Crie os documentos de destino e de origem

 Crie instâncias de`Document` para os documentos de destino e origem.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Passo 3: Mantenha a numeração da fonte ao importar

 Para preservar a formatação de numeração dos parágrafos numerados do documento de origem, crie uma instância de`ImportFormatOptions` E definir`KeepSourceNumbering` para`true` . Use um`NodeImporter` para importar nós do documento de origem para o documento de destino, especificando`ImportFormatMode.KeepSourceFormatting` e a`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Etapa 4: importar e anexar parágrafos

 Itere pelos parágrafos no documento de origem e importe cada parágrafo para o documento de destino usando o comando`importer`. Anexe os nós importados ao corpo do documento de destino.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Etapa 5: salve o documento modificado

 Salve o documento modificado usando o`Save` método do`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Isso completa a implementação de anexar um documento de origem a um documento de destino, mantendo a formatação de numeração original usando Aspose.Words for .NET.

### Exemplo de código-fonte para Keep Source Numbering usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Mantenha a formatação da lista de fontes ao importar parágrafos numerados.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```