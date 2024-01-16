---
title: Definir cor de controle de conteúdo
linktitle: Definir cor de controle de conteúdo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir a cor de um controle de conteúdo em um documento Word usando Aspose.Words for .NET, personalizando sua aparência.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/set-content-control-color/
---

Este tutorial explica como definir a cor de um controle de conteúdo em um documento do Word usando Aspose.Words for .NET. Você pode personalizar a aparência dos controles de conteúdo alterando sua cor.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde seu documento está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregar o documento e recuperar o controle de conteúdo
 Carregue o documento do Word usando o`Document` construtor, passando o caminho para o documento como parâmetro. Recupere o controle de conteúdo desejado do documento. Neste exemplo, assumimos que o controle de conteúdo é a primeira tag de documento estruturada no documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Etapa 3: definir a cor do controle de conteúdo
 Defina a cor do controle de conteúdo atribuindo um`Color` valor para o`Color` propriedade da tag do documento estruturado. Neste exemplo, definimos a cor como vermelho.

```csharp
sdt.Color = Color.Red;
```

## Etapa 4: salve o documento
 Salve o documento modificado no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Exemplo de código-fonte para definir cor de controle de conteúdo usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

É isso! Você definiu com êxito a cor de um controle de conteúdo em seu documento do Word usando Aspose.Words for .NET.