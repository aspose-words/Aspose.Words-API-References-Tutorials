---
title: Limpar controle de conteúdo
linktitle: Limpar controle de conteúdo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como limpar o conteúdo de um controle em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/clear-contents-control/
---

Este tutorial demonstra como limpar o conteúdo de um SDT em um documento do Word usando Aspose.Words for .NET. Limpar o conteúdo de um SDT remove qualquer texto ou nós filhos do controle de conteúdo.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde seu documento está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregue o documento e obtenha a StructuredDocumentTag
 Carregue o documento do Word usando o`Document` construtor, passando o caminho para o documento como parâmetro. Em seguida, recupere o desejado`StructuredDocumentTag`do documento. Neste exemplo, assumimos que o SDT é o primeiro nó filho no documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Etapa 3: limpar o conteúdo da StructuredDocumentTag
 Limpe o conteúdo do SDT usando o`Clear` método. Isso remove qualquer texto ou nós filhos do controle de conteúdo.

```csharp
sdt.Clear();
```

## Etapa 4: salve o documento
 Salve o documento modificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Exemplo de código-fonte para Clear Contents Control usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

É isso! Você limpou com sucesso o conteúdo de um StructuredDocumentTag em seu documento do Word usando Aspose.Words for .NET.