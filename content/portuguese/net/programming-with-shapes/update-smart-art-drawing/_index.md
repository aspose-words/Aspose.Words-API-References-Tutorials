---
title: Atualizar desenho de arte inteligente
linktitle: Atualizar desenho de arte inteligente
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como atualizar o desenho Smart Art em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/update-smart-art-drawing/
---

Este tutorial explica como atualizar o desenho Smart Art em um documento do Word usando Aspose.Words for .NET. Ao iterar pelas formas do documento e verificar se elas possuem Smart Art, você pode atualizar o desenho Smart Art para refletir quaisquer alterações feitas em seus dados.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde seu documento está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregue o documento
 Carregue o documento do Word que contém o desenho Smart Art usando o`Document` construtor de classe.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Etapa 3: atualize o desenho Smart Art
 Itere pelas formas do documento usando o comando`GetChildNodes` método com o`NodeType.Shape` parâmetro. Verifique se cada forma possui Smart Art usando o`HasSmartArt`propriedade e, se for verdade, chame o`UpdateSmartArtDrawing` método para atualizar o desenho Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Exemplo de código-fonte para atualizar o desenho Smart Art usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

É isso! Você atualizou com êxito o desenho Smart Art em seu documento do Word usando Aspose.Words for .NET.