---
title: Ignorar rodapé do cabeçalho
linktitle: Ignorar rodapé do cabeçalho
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como anexar um documento ignorando o conteúdo do cabeçalho e rodapé usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/ignore-header-footer/
---

Este tutorial explica como usar Aspose.Words for .NET para anexar um documento ignorando o conteúdo do cabeçalho e rodapé. O código-fonte fornecido demonstra como configurar as opções de formato de importação para excluir o cabeçalho e o rodapé durante o processo de acréscimo.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

-  Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo em[Aspose.Releases]https://releases.aspose.com/words/net/ ou use o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório de documentos onde os documentos de origem e destino estão localizados.

## Passo 2: Abra os documentos de origem e destino

 Abra os documentos de origem e destino usando o`Document` construtor de classe. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Etapa 3: configurar opções de formato de importação

 Crie uma instância do`ImportFormatOptions` classe e definir o`IgnoreHeaderFooter`propriedade para`false`. Isso garante que o conteúdo do cabeçalho e do rodapé seja incluído durante o processo de acréscimo.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Etapa 4: anexar o documento de origem ao documento de destino

 Use o`AppendDocument` método do documento de destino para anexar o documento de origem. Passar`ImportFormatMode.KeepSourceFormatting` como segundo parâmetro e as opções de formato de importação como terceiro parâmetro.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Etapa 5: salve o documento de destino

 Finalmente, salve o documento de destino modificado usando o`Save` método do`Document` objeto.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Isso completa a implementação de anexar um documento enquanto ignora o conteúdo do cabeçalho e rodapé usando Aspose.Words for .NET.

### Exemplo de código-fonte para Ignore Header Footer usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```