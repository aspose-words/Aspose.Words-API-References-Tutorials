---
title: Definir estilo de controle de conteúdo
linktitle: Definir estilo de controle de conteúdo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir o estilo de um controle de conteúdo em um documento do Word usando Aspose.Words for .NET, aplicando formatação consistente.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/set-content-control-style/
---

Este tutorial explica como definir o estilo de um controle de conteúdo em um documento do Word usando Aspose.Words for .NET. Você pode aplicar estilos predefinidos ou personalizados aos controles de conteúdo para obter uma formatação consistente.

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

## Etapa 3: recuperar o estilo e aplicar ao controle de conteúdo
 Recupere o estilo desejado da coleção de estilos do documento. Neste exemplo, recuperamos o estilo "Quote" usando`StyleIdentifier.Quote` . Em seguida, atribua o estilo recuperado ao`Style` propriedade da tag do documento estruturado.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Etapa 4: salve o documento
 Salve o documento modificado no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Exemplo de código-fonte para definir estilo de controle de conteúdo usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

É isso! Você definiu com êxito o estilo de um controle de conteúdo em seu documento do Word usando Aspose.Words for .NET.