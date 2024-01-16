---
title: Inserir documento com o Builder
linktitle: Inserir documento com o Builder
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um documento no final de outro documento usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/insert-document-with-builder/
---

 Este tutorial explica como usar Aspose.Words for .NET para inserir um documento em outro documento usando o`DocumentBuilder` aula. O código-fonte fornecido demonstra como inserir um documento no final de outro documento preservando a formatação original.

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

## Etapa 3: inicializar o DocumentBuilder

 Crie uma nova instância do`DocumentBuilder` class e passe o documento de destino como parâmetro.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Etapa 4: posicionar o DocumentBuilder

 Mova o`DocumentBuilder` até o final do documento usando o`MoveToDocumentEnd` método. Insira uma quebra de página para separar o conteúdo existente do documento inserido.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Etapa 5: insira o documento de origem

 Use o`InsertDocument` método do`DocumentBuilder` class para inserir o documento de origem no documento de destino. Defina o modo de formato de importação para`ImportFormatMode.KeepSourceFormatting` para preservar a formatação de origem.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 6: salve o documento modificado

 Finalmente, salve o documento de destino modificado usando o`Save` método do`Document` objeto.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Isso completa a implementação da inserção de um documento em outro documento usando Aspose.Words for .NET.

### Exemplo de código-fonte para Inserir documento com Builder usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```