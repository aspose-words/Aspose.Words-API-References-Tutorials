---
title: Imagem
linktitle: Imagem
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir e personalizar imagens com o guia passo a passo Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/image/
---

Neste exemplo, explicaremos como usar o recurso de imagem com Aspose.Words for .NET. As imagens permitem inserir ilustrações e gráficos em um documento.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passo 2: Inserindo uma imagem

 Podemos inserir uma imagem usando o`Shape` classe e especificando o tipo de imagem, aqui`ShapeType.Image` . Também definimos o tipo de quebra da imagem como`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Etapa 3: personalização da imagem

 Personalizamos a imagem especificando seu caminho completo, por exemplo`"/attachment/1456/pic001.png"`e adicionando um título à imagem.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Exemplo de código-fonte para imagens com Aspose.Words for .NET

```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

// Inserir Imagem.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Parabéns! Agora você aprendeu como usar o recurso de imagens com Aspose.Words for .NET.


### Perguntas frequentes

#### P: Como posso inserir uma imagem de um arquivo local no Aspose.Words?

 R: Para inserir uma imagem de um arquivo local no Aspose.Words, você pode usar o`Shape` classe e o`InsertImage` método.

#### P: Posso inserir uma imagem de um URL no Aspose.Words?

 R: Sim, você pode inserir uma imagem de um URL no Aspose.Words. Você pode usar o mesmo`InsertImage` especifique o URL da imagem em vez do caminho do arquivo local.

#### P: Como posso redimensionar uma imagem no Aspose.Words?

 R: Para redimensionar uma imagem no Aspose.Words, você pode usar o`Width`e`Height` propriedades do`Shape` objeto.

#### P: Posso aplicar filtros a imagens no Aspose.Words?

 R: Sim, você pode aplicar filtros a imagens no Aspose.Words. Por exemplo, você pode aplicar um filtro de desfoque a uma imagem usando o`ApplyGaussianBlur` método do`Shape` objeto.

#### P: Como posso substituir uma imagem por outra no Aspose.Words?

 R: Para substituir uma imagem por outra no Aspose.Words, você pode usar o`Replace` método do`Shape` aula. Este método toma como parâmetro o`Shape` objeto da imagem a ser substituída e o`Shape` objeto da nova imagem.