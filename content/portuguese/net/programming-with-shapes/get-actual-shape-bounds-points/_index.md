---
title: Obtenha pontos reais de limites de forma
linktitle: Obtenha pontos reais de limites de forma
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como recuperar os limites reais de uma forma em pontos (unidade de medida) em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Este tutorial explica como recuperar os limites reais de uma forma em pontos (unidade de medida) em um documento do Word usando Aspose.Words for .NET. Os limites representam o tamanho e a posição da forma no documento.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: Crie um novo documento e DocumentBuilder
 Crie uma nova instância do`Document` aula e um`DocumentBuilder`objeto para trabalhar com o documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir um formato de imagem
 Use o`InsertImage` método do`DocumentBuilder` objeto para inserir uma forma de imagem no documento. Forneça o caminho para o arquivo de imagem como parâmetro.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Etapa 3: recuperar pontos reais de limites de forma
 Acesse a forma`ShapeRenderer` usando o`GetShapeRenderer` método. Em seguida, recupere os limites reais da forma em pontos usando o método`BoundsInPoints` propriedade.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Exemplo de código-fonte para obter pontos reais de limites de forma usando Aspose.Words for .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

É isso! Você recuperou com êxito os limites reais de uma forma em pontos em seu documento do Word usando Aspose.Words for .NET.