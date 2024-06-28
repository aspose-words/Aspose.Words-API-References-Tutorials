---
title: Inserir forma
linktitle: Inserir forma
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir formas em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/insert-shape/
---

Este tutorial explica como inserir formas em um documento do Word usando Aspose.Words for .NET. As formas podem ser usadas para aprimorar a aparência visual e o layout dos seus documentos.

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

## Etapa 3: inserir formas
 Use o`InsertShape` método do`DocumentBuilder`objeto para inserir formas no documento. Especifique o tipo de forma, as posições horizontais e verticais relativas, as dimensões da página, o tamanho e o tipo de quebra automática. Você também pode definir o ângulo de rotação das formas, se desejar.

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## Etapa 4: salve o documento
 Salve o documento no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithShapes.InsertShape.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### Exemplo de código-fonte para Insert Shape usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
		RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
	shape.Rotation = 30.0;
	builder.Writeln();
	shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
	shape.Rotation = 30.0;
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

É isso! Você inseriu formas com sucesso em seu documento do Word usando Aspose.Words for .NET.