---
title: Configuração de página diferente
linktitle: Configuração de página diferente
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como anexar um documento com diferentes configurações de página usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/different-page-setup/
---

Este tutorial explica como usar Aspose.Words for .NET para anexar um documento com diferentes configurações de configuração de página a outro documento. O código-fonte fornecido demonstra como definir diferentes configurações de página para os documentos de origem e destino e garantir a continuação e numeração adequadas.

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

## Etapa 3: definir as configurações de página do documento de origem

 Ajuste as configurações de página do documento de origem para garantir a continuação e numeração adequadas. Neste exemplo, definimos o início da seção como`SectionStart.Continuous` e reinicie a numeração de páginas. Também nos certificamos de que a largura, altura e orientação da página correspondam à última seção do documento de destino.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Etapa 4: modificar a formatação do parágrafo

 Para manter a formatação adequada, percorra todos os parágrafos do documento de origem e defina o`KeepWithNext`propriedade para`true`Isso garante que os parágrafos permaneçam juntos durante o processo de anexação.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Etapa 5: anexar o documento de origem ao documento de destino

 Use o`AppendDocument` método do documento de destino para anexar o documento de origem modificado ao documento de destino, preservando a formatação de origem.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 6: salve o documento de destino

 Finalmente, salve o documento de destino modificado usando o`Save` método do`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Isso conclui a implementação de anexar um documento com diferentes configurações de configuração de página usando Aspose.Words for .NET.

### Exemplo de código-fonte para configuração de página diferente usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Defina o documento de origem para continuar logo após o final do documento de destino.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Reinicie a numeração de páginas no início do documento de origem.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Para garantir que isso não aconteça quando o documento de origem tiver configurações de página diferentes, certifique-se de que o
	// as configurações são idênticas entre a última seção do documento de destino.
	// Se houver outras seções contínuas no documento de origem,
	//isso precisará ser repetido para essas seções.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Itere por todas as seções do documento de origem.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```