---
title: Ignorar caixas de texto
linktitle: Ignorar caixas de texto
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como anexar um documento ignorando a formatação da caixa de texto usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/ignore-text-boxes/
---

Este tutorial explica como usar Aspose.Words for .NET para anexar um documento enquanto preserva a formatação das caixas de texto. O código-fonte fornecido demonstra como configurar as opções de formato de importação para incluir caixas de texto durante o processo de acréscimo.

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

## Etapa 3: configurar opções de formato de importação

 Crie uma instância do`ImportFormatOptions` classe e definir o`IgnoreTextBoxes`propriedade para`false`. Isso garante que as caixas de texto sejam incluídas durante o processo de acréscimo, preservando sua formatação.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Etapa 4: anexar o conteúdo da caixa de texto

 Criar uma`NodeImporter` objeto e use-o para importar nós de caixa de texto do documento de origem para o documento de destino. Itere cada parágrafo no documento de origem e importe-o para o documento de destino.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Etapa 5: salve o documento de destino

 Finalmente, salve o documento de destino modificado usando o`Save` método do`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Isso completa a implementação de anexar um documento enquanto preserva a formatação da caixa de texto usando Aspose.Words for .NET.

### Exemplo de código-fonte para Ignorar caixas de texto usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Mantenha a formatação das caixas de texto de origem ao importar.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```