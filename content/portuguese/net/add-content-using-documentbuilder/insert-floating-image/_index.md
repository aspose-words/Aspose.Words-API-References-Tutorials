---
title: Insira imagem flutuante em documento do Word
linktitle: Insira imagem flutuante em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir imagens flutuantes em documentos do Word usando Aspose.Words for .NET. Guia passo a passo.
type: docs
weight: 10
url: /pt/net/add-content-using-documentbuilder/insert-floating-image/
---
Neste exemplo abrangente, você aprenderá como inserir uma imagem flutuante em um documento do Word usando Aspose.Words for .NET. Orientaremos você durante o processo e forneceremos os trechos de código C# necessários. Ao final deste guia, você poderá adicionar imagens com opções personalizáveis de posicionamento e quebra automática aos seus documentos.

## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Words for .NET instalada em seu sistema.

## Etapa 1: Crie um novo documento e DocumentBuilder
Para começar, crie um novo documento usando a classe Document e inicialize um objeto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir uma imagem flutuante
A seguir, use o método InsertImage da classe DocumentBuilder para inserir uma imagem flutuante. Forneça o caminho do arquivo de imagem, posição relativa horizontal e vertical, largura, altura e opções de quebra automática como parâmetros:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Etapa 3: salve o documento
Após inserir a imagem flutuante, salve o documento em um arquivo usando o método Save da classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Exemplo de código-fonte para inserir imagem flutuante usando Aspose.Words para .NET
Aqui está o código-fonte completo para inserir uma imagem flutuante usando Aspose.Words for .NET:
As imagens flutuantes são úteis para vários cenários, como adicionar logotipos, ilustrações ou elementos decorativos que podem ser posicionados independentemente do texto do documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

Lembre-se de ajustar o código de acordo com seus requisitos específicos, incluindo o caminho do arquivo de imagem e as opções desejadas de posicionamento e quebra automática.

## Conclusão
Parabéns! Você aprendeu com sucesso como inserir uma imagem flutuante em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e utilizando o código-fonte fornecido, agora você pode aprimorar seus documentos com imagens flutuantes visualmente atraentes e personalizáveis.

### Perguntas frequentes para inserir imagem flutuante em documento do Word

#### P: Posso inserir várias imagens flutuantes em um único documento?

R: Certamente! Você pode inserir quantas imagens flutuantes forem necessárias em um documento do Word usando Aspose.Words for .NET. Basta repetir o processo de inserção para adicionar várias imagens visualmente atraentes.

#### P: Quais opções de encapsulamento estão disponíveis para a imagem flutuante?

R: Aspose.Words for .NET oferece várias opções de encapsulamento para imagens flutuantes, incluindo Square, Tight, Through, TopBottom e None. Estas opções determinam como o texto interage com a imagem flutuante.

#### P: Posso ajustar o tamanho da imagem flutuante?

R: Absolutamente! Você pode especificar a largura e a altura da imagem flutuante usando os respectivos parâmetros no método InsertImage. Isso permite controlar as dimensões da imagem de acordo com suas preferências de design.

#### P: Posso posicionar a imagem flutuante em relação a um elemento específico do documento?

R: Sim, Aspose.Words for .NET permite posicionar a imagem flutuante em relação a elementos específicos, como margem, página, parágrafo ou tabela. Você pode escolher os parâmetros de posição relativa horizontal e vertical apropriados para obter o posicionamento desejado.

#### P: O Aspose.Words for .NET é adequado para aplicativos desktop e web?

R: Sim, Aspose.Words for .NET é uma biblioteca versátil adequada para aplicativos desktop e web. Esteja você construindo um aplicativo Windows ou um sistema baseado na Web, você pode integrar a biblioteca sem esforço.
