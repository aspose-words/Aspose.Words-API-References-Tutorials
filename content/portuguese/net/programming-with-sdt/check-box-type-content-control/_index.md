---
title: Controle de conteúdo do tipo de caixa de seleção
linktitle: Controle de conteúdo do tipo de caixa de seleção
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar um controle de conteúdo do tipo caixa de seleção em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/check-box-type-content-control/
---

Este tutorial explica como criar um controle de conteúdo do tipo caixa de seleção em um documento do Word usando Aspose.Words for .NET. Os controles de conteúdo da caixa de seleção permitem que os usuários marquem ou desmarquem uma caixa de seleção no documento.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Crie um Documento e DocumentBuilder
 Crie uma nova instância do`Document` aula e um`DocumentBuilder` para construir o conteúdo do documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: adicionar um controle de conteúdo do tipo caixa de seleção
 Criar uma`StructuredDocumentTag` com`SdtType.Checkbox` para representar o controle de conteúdo da caixa de seleção. Especificamos`MarkupLevel.Inline` para colocá-lo dentro do texto.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Etapa 4: salve o documento
 Salve o documento no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Exemplo de código-fonte para controle de conteúdo do tipo caixa de seleção usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

É isso! Você criou com sucesso um controle de conteúdo do tipo caixa de seleção em seu documento do Word usando Aspose.Words for .NET.