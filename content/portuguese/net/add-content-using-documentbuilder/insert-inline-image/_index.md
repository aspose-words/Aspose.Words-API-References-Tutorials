---
title: Inserir imagem embutida em documento do Word
linktitle: Inserir imagem embutida em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir imagens embutidas em documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/insert-inline-image/
---
Neste tutorial abrangente, você aprenderá como inserir imagens embutidas em um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você poderá adicionar imagens diretamente no texto dos seus documentos.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: Crie um novo documento e DocumentBuilder
Para começar, crie um novo documento usando a classe Document e inicialize um objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir uma imagem embutida
A seguir, use o método InsertImage da classe DocumentBuilder para inserir uma imagem embutida no documento. Forneça o caminho do arquivo de imagem como parâmetro:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Etapa 3: salve o documento
Após inserir a imagem embutida, salve o documento em um arquivo usando o método Save da classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Exemplo de código-fonte para inserir imagem embutida usando Aspose.Words para .NET
Aqui está o código-fonte completo para inserir uma imagem embutida usando Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Conclusão
Parabéns! Você aprendeu com sucesso como inserir imagens embutidas em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode adicionar imagens perfeitamente ao texto de seus documentos.

As imagens embutidas são úteis para vários cenários, como adicionar ilustrações, logotipos ou outros elementos visuais diretamente no fluxo do documento.

### Perguntas frequentes para inserir imagem embutida em documento do Word

#### P: Posso redimensionar as imagens embutidas no documento do Word?

R: Sim, você pode redimensionar as imagens embutidas usando Aspose.Words for .NET. Após inserir a imagem, você pode manipular seu tamanho ajustando as propriedades de largura e altura do objeto Shape que representa a imagem.

#### P: É possível adicionar texto alternativo a imagens embutidas para fins de acessibilidade?

R: Sim, você pode adicionar texto alternativo a imagens embutidas para melhorar a acessibilidade. Aspose.Words for .NET suporta a adição de texto alternativo às imagens, permitindo que leitores de tela e outras tecnologias assistivas descrevam o conteúdo da imagem para usuários com deficiência visual.

#### P: Posso aplicar formatação ou estilos às imagens embutidas?

R: Absolutamente! Aspose.Words for .NET oferece amplas opções de formatação para imagens embutidas. Você pode aplicar vários estilos, bordas, efeitos e outros atributos de formatação às imagens para combinar com o design visual do seu documento.

#### P: O Aspose.Words for .NET oferece suporte à inserção de imagens de um fluxo ou matriz de bytes?

R: Sim, você pode inserir imagens embutidas de fluxos ou matrizes de bytes usando Aspose.Words for .NET. Isso permite trabalhar com imagens carregadas de fontes externas ou imagens geradas dinamicamente.

#### P: Posso inserir imagens em posições específicas no conteúdo do texto?

R: Sim, a classe DocumentBuilder em Aspose.Words for .NET fornece controle preciso sobre a posição de inserção de imagens embutidas. Você pode especificar o local exato no texto onde a imagem deve ser inserida.