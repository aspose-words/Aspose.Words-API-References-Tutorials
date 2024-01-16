---
title: Modificar controles de conteúdo
linktitle: Modificar controles de conteúdo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como modificar texto, listas suspensas e imagens dentro de controles de conteúdo em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/modify-content-controls/
---

Este tutorial explica como modificar diferentes tipos de controles de conteúdo em um documento do Word usando Aspose.Words for .NET. Você pode atualizar o texto, o valor selecionado de uma lista suspensa ou substituir uma imagem nos controles de conteúdo.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde seu documento está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregar o documento e iterar sobre os controles de conteúdo
 Carregue o documento do Word usando o`Document`construtor, passando o caminho para o documento como parâmetro. Itere sobre todas as tags de documento estruturadas no documento usando um`foreach` laço.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Execute ações com base no tipo de controle de conteúdo
}
```

## Etapa 3: modificar o controle de conteúdo de texto simples
 Para controles de conteúdo do tipo`SdtType.PlainText`, remova todos os filhos existentes, crie um novo parágrafo e anexe uma execução com o texto desejado.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Etapa 4: modificar o controle de conteúdo da lista suspensa
 Para controles de conteúdo do tipo`SdtType.DropDownList` , atualize o valor selecionado definindo-o para um valor específico`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Etapa 5: modificar o controle de conteúdo de imagem
 Para controles de conteúdo do tipo`SdtType.Picture`, recupere a forma dentro do controle de conteúdo e substitua sua imagem por uma nova.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Etapa 6: salve o documento modificado
 Salve o documento modificado no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Exemplo de código-fonte para modificar controles de conteúdo usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

É isso! Você modificou com sucesso diferentes tipos de controles de conteúdo em seu documento do Word usando Aspose.Words for .NET.