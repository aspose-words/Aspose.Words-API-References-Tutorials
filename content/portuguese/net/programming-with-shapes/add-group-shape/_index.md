---
title: Adicionar forma de grupo
linktitle: Adicionar forma de grupo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar uma forma de grupo com múltiplas formas a um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/add-group-shape/
---

Este tutorial explica como adicionar uma forma de grupo contendo várias formas a um documento do Word usando Aspose.Words for .NET. As formas de grupo permitem combinar e manipular várias formas como uma única entidade.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: crie um novo documento e GroupShape
 Crie uma nova instância do`Document` classe e`GroupShape`objeto para trabalhar com o documento.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Etapa 3: criar e adicionar formas ao GroupShape
 Crie formas individuais, como`accentBorderShape` e`actionButtonShape` usando o`Shape` aula. Personalize suas propriedades conforme desejado. Anexe essas formas ao`groupShape` objeto.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Etapa 4: definir dimensões para GroupShape
 Defina a largura, a altura e o tamanho das coordenadas para o`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Etapa 5: insira o GroupShape no documento
 Criar uma`DocumentBuilder` objeto e insira o`groupShape` no documento usando o`InsertNode` método.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Etapa 6: salve o documento
 Salve o documento no diretório especificado usando o`Save`método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Exemplo de código-fonte para Adicionar forma de grupo usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

É isso! Você adicionou com sucesso uma forma de grupo contendo várias formas ao seu documento do Word usando Aspose.W