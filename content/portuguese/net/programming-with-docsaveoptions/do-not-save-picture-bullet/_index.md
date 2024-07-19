---
title: Não salve o marcador da imagem
linktitle: Não salve o marcador da imagem
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como lidar com marcadores de imagens no Aspose.Words for .NET com nosso guia passo a passo. Simplifique o gerenciamento de documentos e crie documentos profissionais do Word sem esforço.
type: docs
weight: 10
url: /pt/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---
## Introdução

Olá, colegas desenvolvedores! Você já trabalhou com documentos do Word e se viu envolvido nas complexidades de salvar marcadores de imagens? É um daqueles pequenos detalhes que podem fazer uma grande diferença na aparência final do seu documento. Bem, hoje estou aqui para guiá-lo através do processo de manipulação de marcadores de imagem no Aspose.Words for .NET, focando principalmente no recurso "Não salvar marcador de imagem". Pronto para mergulhar? Vamos!

## Pré-requisitos

Antes de começarmos a mexer no código, há algumas coisas que você precisa ter em mente:

1.  Aspose.Words for .NET: Certifique-se de ter esta poderosa biblioteca instalada. Se você ainda não tem, pode baixá-lo[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: um ambiente de desenvolvimento .NET funcional, como o Visual Studio.
3. Conhecimento básico de C#: Alguma familiaridade com programação C# será útil.
4. Documento de amostra: um documento do Word com marcadores de imagem para fins de teste.

## Importar namespaces

Para começar, você precisa importar os namespaces necessários. Isso é bastante simples, mas crucial para acessar as funcionalidades do Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Vamos dividir o processo em etapas gerenciáveis. Dessa forma, você pode acompanhar facilmente e entender cada parte do código.

## Etapa 1: configure seu diretório de documentos

Em primeiro lugar, você precisa especificar o caminho para o diretório de documentos. É aqui que seus documentos do Word são armazenados e onde você salvará os arquivos modificados.

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real em seu sistema onde seus documentos estão localizados.

## Etapa 2: carregar o documento com marcadores de imagem

A seguir, você carregará o documento do Word que contém marcadores de imagem. Este documento será modificado para remover os marcadores da imagem quando salvo.

```csharp
// Carregue o documento com marcadores de imagem
Document doc = new Document(dataDir + "Image bullet points.docx");
```

 Certifique-se de que o arquivo`"Image bullet points.docx"` existe no diretório especificado.

## Etapa 3: configurar opções de salvamento

Agora, vamos configurar as opções de salvamento para especificar que os marcadores da imagem não devem ser salvos. É aqui que a mágica acontece!

```csharp
// Configure as opções de salvamento com o recurso "Não salvar marcador de imagem"
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

 Definindo`SavePictureBullet` para`false`, você instrui o Aspose.Words a não salvar marcadores de imagem no documento de saída.

## Etapa 4: salve o documento

Finalmente, salve o documento com as opções especificadas. Isso irá gerar um novo arquivo onde os marcadores da imagem não estão incluídos.

```csharp
// Salve o documento com as opções especificadas
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

 O novo arquivo,`"WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx"`, será salvo em seu diretório de documentos.

## Conclusão

E aí está! Com apenas algumas linhas de código, você configurou com sucesso o Aspose.Words for .NET para omitir marcadores de imagem ao salvar um documento. Isso pode ser extremamente útil quando você precisa de uma aparência limpa e consistente, sem a distração dos marcadores de imagem.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa para criar, editar e converter documentos Word em aplicativos .NET.

### Posso usar esse recurso para outros tipos de marcadores?
Não, esse recurso específico é para marcadores de imagens. No entanto, Aspose.Words oferece amplas opções para lidar com outros tipos de marcadores.

### Onde posso obter suporte para Aspose.Words?
 Você pode obter suporte do[Fórum Aspose.Words](https://forum.aspose.com/c/words/8).

### Existe uma avaliação gratuita do Aspose.Words for .NET?
 Sim, você pode obter um teste gratuito[aqui](https://releases.aspose.com/).

### Como faço para adquirir uma licença do Aspose.Words for .NET?
 Você pode comprar uma licença no[Aspose Loja](https://purchase.aspose.com/buy).
