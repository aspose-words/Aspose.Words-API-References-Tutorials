---
title: Formato 1Bpp Indexado
linktitle: Formato 1Bpp Indexado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como converter um documento do Word em uma imagem indexada de 1Bpp usando Aspose.Words for .NET. Siga nosso guia passo a passo para fácil conversão.
type: docs
weight: 10
url: /pt/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
## Introdução

Já se perguntou como salvar um documento do Word como uma imagem em preto e branco com apenas algumas linhas de código? Bem, você está com sorte! Hoje, estamos mergulhando em um pequeno truque usando Aspose.Words for .NET que permite converter seus documentos em imagens indexadas de 1Bpp. Este formato é perfeito para determinados tipos de arquivamento digital, impressão ou quando você precisa economizar espaço. Descreveremos cada etapa para torná-la tão fácil quanto uma torta. Pronto para começar? Vamos mergulhar!

## Pré-requisitos

Antes de sujarmos as mãos, há algumas coisas que você precisa ter em mente:

-  Aspose.Words for .NET: Certifique-se de ter a biblioteca instalada. Você pode[baixe aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento .NET: Visual Studio é uma boa opção, mas você pode usar qualquer ambiente com o qual se sinta confortável.
- Conhecimento básico de C#: não se preocupe, vamos mantê-lo simples, mas um pouco de familiaridade com C# ajudará.
- Um documento do Word: tenha um documento do Word de amostra pronto para ser convertido.

## Importar namespaces

Em primeiro lugar, precisamos importar os namespaces necessários. Isso é crucial porque nos permite acessar as classes e métodos que precisamos do Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: configure seu diretório de documentos

Você precisará especificar o caminho para o diretório do seu documento. É aqui que o seu documento Word é armazenado e onde a imagem convertida será salva.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregue o documento do Word

 Agora, vamos carregar o documento do Word em um Aspose.Words`Document` objeto. Este objeto representa seu arquivo Word e permite manipulá-lo.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 3: configurar opções para salvar imagens

 Em seguida, precisamos configurar o`ImageSaveOptions`É aqui que a mágica acontece. Vamos configurá-lo para salvar a imagem no formato PNG com modo de cores indexadas de 1Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1),
    ImageColorMode = ImageColorMode.BlackAndWhite,
    PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

- SaveFormat.Png: especifica que queremos salvar o documento como uma imagem PNG.
- PageSet(1): indica que estamos convertendo apenas a primeira página.
- ImageColorMode.BlackAndWhite: Isso define a imagem para preto e branco.
- ImagePixelFormat.Format1bppIndexed: define o formato da imagem para 1Bpp indexado.

## Etapa 4: salve o documento como imagem

 Por fim, salvamos o documento como uma imagem usando o`Save` método do`Document` objeto.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

## Conclusão

E aí está! Com apenas algumas linhas de código, você transformou seu documento do Word em uma imagem indexada de 1Bpp usando Aspose.Words for .NET. Este método é extremamente útil para criar imagens de alto contraste e com uso eficiente de espaço a partir de seus documentos. Agora, você pode integrar isso facilmente aos seus projetos e fluxos de trabalho. Boa codificação!

## Perguntas frequentes

### O que é uma imagem indexada de 1Bpp?
Uma imagem indexada de 1Bpp (1 bit por pixel) é um formato de imagem em preto e branco onde cada pixel é representado por um único bit, 0 ou 1. Este formato é altamente eficiente em termos de espaço.

### Posso converter várias páginas de um documento do Word de uma só vez?
 Sim, você pode. Modifique o`PageSet` propriedade no`ImageSaveOptions` para incluir várias páginas ou o documento inteiro.

### Preciso de uma licença para usar o Aspose.Words for .NET?
 Sim, Aspose.Words for .NET requer uma licença para funcionalidade completa. Você pode obter um[licença temporária aqui](https://purchase.aspose.com/temporary-license/).

### Para quais outros formatos de imagem posso converter meu documento do Word?
 Aspose.Words suporta vários formatos de imagem, incluindo JPEG, BMP e TIFF. Basta alterar o`SaveFormat` no`ImageSaveOptions`.

### Onde posso encontrar mais documentação sobre Aspose.Words for .NET?
 Você pode encontrar documentação detalhada no[Página de documentação do Aspose.Words para .NET](https://reference.aspose.com/words/net/).
