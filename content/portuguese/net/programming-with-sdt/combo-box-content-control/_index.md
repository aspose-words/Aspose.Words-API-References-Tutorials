---
title: Controle de conteúdo da caixa de combinação
linktitle: Controle de conteúdo da caixa de combinação
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar um controle de conteúdo de caixa de combinação em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/combo-box-content-control/
---

Este tutorial explica como criar um controle de conteúdo de caixa de combinação em um documento do Word usando Aspose.Words for .NET. Os controles de conteúdo da caixa de combinação permitem que os usuários selecionem um item em uma lista suspensa.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"`com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: crie um documento e uma StructuredDocumentTag
 Crie uma nova instância do`Document` aula e um`StructuredDocumentTag` para representar o controle de conteúdo da caixa de combinação. Especificamos`SdtType.ComboBox` como o tipo e`MarkupLevel.Block` como o nível de marcação para criar uma caixa de combinação em nível de bloco.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Etapa 3: adicionar itens à caixa de combinação
 Adicione itens à caixa de combinação usando o`ListItems` propriedade do`StructuredDocumentTag` . Cada item é representado por um`SdtListItem` objeto, que recebe um texto de exibição e um valor. Neste exemplo, adicionamos três itens à caixa de combinação.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Etapa 4: anexar o StructuredDocumentTag ao documento
 Anexe o controle de conteúdo da caixa de combinação ao corpo do documento usando o comando`AppendChild` método do corpo da primeira seção do documento.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Etapa 5: salve o documento
 Salve o documento no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Exemplo de código-fonte para controle de conteúdo de caixa de combinação usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

É isso! Você criou com sucesso um controle de conteúdo de caixa de combinação em seu documento do Word usando Aspose.Words for .NET.