---
title: Controle de conteúdo de caixa de rich text
linktitle: Controle de conteúdo de caixa de rich text
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar um controle de conteúdo de caixa de rich text em um documento do Word usando Aspose.Words for .NET, permitindo formatação e estilo de texto.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/rich-text-box-content-control/
---

Este tutorial demonstra como criar um controle de conteúdo de caixa de rich text em um documento do Word usando Aspose.Words for .NET. Os controles de conteúdo de caixa de rich text permitem que os usuários insiram e formatem texto com vários estilos e opções de formatação.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: crie um documento e uma StructuredDocumentTag
 Crie uma nova instância do`Document` aula e um`StructuredDocumentTag` para representar o controle de conteúdo da caixa de rich text. Especificamos`SdtType.RichText` como o tipo e`MarkupLevel.Block` como o nível de marcação para criar uma caixa de rich text em nível de bloco.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Etapa 3: criar e formatar o conteúdo Rich Text
Crie um parágrafo e execute-o para representar o conteúdo rich text. Defina as opções de texto e formatação, como cor, fonte, etc.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Etapa 4: adicionar o conteúdo Rich Text ao controle de conteúdo
 Adicione o parágrafo com o conteúdo rich text ao`ChildNodes` coleção do controle de conteúdo da caixa de rich text.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Etapa 5: anexar o controle de conteúdo ao documento
 Anexe o controle de conteúdo da caixa de rich text ao corpo do documento usando o comando`AppendChild` método do corpo da primeira seção do documento.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Etapa 6: salve o documento
 Salve o documento no diretório especificado usando o`Save`método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Exemplo de código-fonte para controle de conteúdo de caixa de rich text usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

É isso! Você criou com êxito um controle de conteúdo de caixa de rich text em seu documento do Word usando Aspose.Words for .NET.