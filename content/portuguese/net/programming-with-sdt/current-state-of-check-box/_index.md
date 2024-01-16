---
title: Caixa de seleção Estado atual
linktitle: Caixa de seleção Estado atual
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como recuperar e definir o estado atual de um controle de conteúdo de caixa de seleção em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/current-state-of-check-box/
---

Este tutorial explica como recuperar e definir o estado atual de um controle de conteúdo de caixa de seleção em um documento do Word usando Aspose.Words for .NET. Você pode marcar ou desmarcar a caixa de seleção com base em seu estado atual.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde seu documento está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregar o documento e recuperar o controle de conteúdo da caixa de seleção
 Carregue o documento do Word usando o`Document` construtor, passando o caminho para o documento como parâmetro. Em seguida, recupere o controle de conteúdo da caixa de seleção desejada do documento. Neste exemplo, assumimos que a caixa de seleção é a primeira tag de documento estruturada no documento.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Etapa 3: marque ou desmarque a caixa de seleção com base em seu estado atual
 Verifique se a tag do documento estruturado recuperada é do tipo`SdtType.Checkbox` . Se estiver, defina o`Checked` propriedade do controle de conteúdo para`true` para marcar a caixa. Caso contrário, você pode deixá-lo desmarcado.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Etapa 4: salve o documento
 Salve o documento modificado no diretório especificado usando o`Save`método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Exemplo de código-fonte para o estado atual da caixa de seleção usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Obtenha o primeiro controle de conteúdo do documento.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

É isso! Você recuperou e definiu com êxito o estado atual de um controle de conteúdo de caixa de seleção em seu documento do Word usando Aspose.Words for .NET.