---
title: Seção múltipla
linktitle: Seção múltipla
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como recuperar e processar tags de documentos estruturados de várias seções em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/multi-section/
---

Este tutorial explica como trabalhar com tags de documentos estruturados de várias seções em um documento do Word usando Aspose.Words for .NET. Você pode recuperar e processar as tags de seção presentes no documento.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde seu documento está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregar o documento e recuperar tags de várias seções
 Carregue o documento do Word usando o`Document` construtor, passando o caminho para o documento como parâmetro. Recupere todos os nós iniciais do intervalo de tags do documento estruturado no documento usando o comando`GetChildNodes` método.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Etapa 3: processar as tags de múltiplas seções
Itere através da coleção de nós iniciais do intervalo de tags de documento estruturado. Neste exemplo, simplesmente imprimimos o título de cada tag no console. Você pode realizar processamento adicional com base em seus requisitos.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Exemplo de código-fonte para Multi Section usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

É isso! Você recuperou e processou com êxito tags de documentos estruturados de várias seções em seu documento do Word usando Aspose.Words for .NET.