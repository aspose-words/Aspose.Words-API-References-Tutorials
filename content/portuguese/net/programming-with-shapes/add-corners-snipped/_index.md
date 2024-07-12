---
title: Adicionar cantos recortados
linktitle: Adicionar cantos recortados
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar uma forma com cantos cortados a um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/add-corners-snipped/
---

 Este tutorial explica como adicionar uma forma com cantos cortados a um documento do Word usando Aspose.Words for .NET. A forma recortada dos cantos pode ser personalizada e inserida usando o`InsertShape` método.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"`com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Crie um novo documento e DocumentBuilder
 Crie uma nova instância do`Document` aula e um`DocumentBuilder` objeto para trabalhar com o documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: insira a forma recortada dos cantos
 Use o`InsertShape` método do`DocumentBuilder` objeto para inserir uma forma com cantos cortados. Especifique o tipo de forma (neste caso,`ShapeType.TopCornersSnipped`) e forneça o tamanho desejado para a forma.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Etapa 4: salve o documento
 Salve o documento no diretório especificado usando o`Save`método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Exemplo de código-fonte para adicionar cantos cortados usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

É isso! Você adicionou com sucesso uma forma de cantos recortados ao seu documento do Word usando Aspose.Words for .NET.