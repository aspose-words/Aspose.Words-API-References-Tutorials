---
title: Âncora vertical
linktitle: Âncora vertical
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como posicionar uma forma verticalmente em um documento usando o recurso de âncora vertical no Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/vertical-anchor/
---

Este tutorial explica como usar o recurso de âncora vertical no Aspose.Words for .NET para posicionar uma forma verticalmente dentro de um documento. Ao definir a propriedade de âncora vertical de uma forma, você pode controlar seu alinhamento vertical em relação ao texto ou à página.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Crie um novo documento e DocumentBuilder
 Crie uma nova instância do`Document` aula e um`DocumentBuilder` objeto para trabalhar com o documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: inserir e configurar uma forma
 Insira uma forma no documento usando o`InsertShape` método do`DocumentBuilder` objeto. Defina as dimensões desejadas para a forma.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Etapa 4: definir a âncora vertical
Defina a propriedade de âncora vertical da forma para controlar seu alinhamento vertical. Neste exemplo, definimos como “Inferior” para ancorar a forma na parte inferior do texto ou página.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Etapa 5: adicionar conteúdo à forma
 Use o`MoveTo` método do`DocumentBuilder` objeto para mover o cursor para o primeiro parágrafo da forma. Então, use o`Write` método para adicionar conteúdo à forma.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Etapa 6: salve o documento
 Salve o documento no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Exemplo de código-fonte para Vertical Anchor usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

É isso! Você usou com sucesso o recurso de âncora vertical no Aspose.Words for .NET para posicionar uma forma verticalmente em um documento.