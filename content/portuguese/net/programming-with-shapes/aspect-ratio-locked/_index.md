---
title: Proporção bloqueada
linktitle: Proporção bloqueada
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como bloquear a proporção de formas em documentos do Word usando Aspose.Words for .NET. Siga este guia passo a passo para manter suas imagens e formas proporcionais.
type: docs
weight: 10
url: /pt/net/programming-with-shapes/aspect-ratio-locked/
---
## Introdução

Você já se perguntou como manter as proporções perfeitas de imagens e formas em seus documentos do Word? Às vezes, você precisa garantir que suas imagens e formas não fiquem distorcidas quando redimensionadas. É aqui que o bloqueio da proporção é útil. Neste tutorial, exploraremos como definir a proporção de formas em documentos do Word usando Aspose.Words for .NET. Dividiremos tudo em etapas fáceis de seguir, garantindo que você possa aplicar essas habilidades aos seus projetos com confiança.

## Pré-requisitos

Antes de mergulharmos no código, vamos ver o que você precisa para começar:

- Biblioteca Aspose.Words for .NET: Você precisa ter o Aspose.Words for .NET instalado. Se ainda não o fez, você pode[baixe aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento .NET configurado. Visual Studio é uma escolha popular.
- Conhecimento básico de C#: Alguma familiaridade com programação C# será útil.

## Importar namespaces

Primeiramente, vamos importar os namespaces necessários. Esses namespaces nos darão acesso às classes e métodos necessários para trabalhar com documentos e formas do Word.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Etapa 1: configure seu diretório de documentos

 Antes de começarmos a manipular formas, precisamos configurar um diretório onde nossos documentos serão armazenados. Por uma questão de simplicidade, usaremos um espaço reservado`YOUR DOCUMENT DIRECTORY`. Substitua isso pelo caminho real para o diretório do seu documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: crie um novo documento

A seguir, criaremos um novo documento do Word usando Aspose.Words. Este documento servirá como tela para adicionar formas e imagens.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aqui, criamos uma instância do`Document` classe e usar um`DocumentBuilder` para nos ajudar a construir o conteúdo do documento.

## Etapa 3: insira uma imagem

 Agora, vamos inserir uma imagem em nosso documento. Usaremos o`InsertImage` método do`DocumentBuilder`aula. Certifique-se de ter uma imagem no diretório especificado.

```csharp
Shape shape = builder.InsertImage(dataDir + "Transparent background logo.png");
```

 Substituir`dataDir + "Transparent background logo.png"` com o caminho para o seu arquivo de imagem.

## Etapa 4: bloquear a proporção

Depois que a imagem for inserida, podemos bloquear sua proporção. O bloqueio da proporção garante que as proporções da imagem permaneçam constantes durante o redimensionamento.

```csharp
shape.AspectRatioLocked = true;
```

 Contexto`AspectRatioLocked` para`true` garante que a imagem mantenha sua proporção original.

## Etapa 5: salve o documento

Finalmente, salvaremos o documento no diretório especificado. Esta etapa grava todas as alterações que fizemos no arquivo do documento.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

## Conclusão

Parabéns! Você aprendeu com sucesso como definir a proporção de formas em documentos do Word usando Aspose.Words for .NET. Seguindo essas etapas, você pode garantir que suas imagens e formas mantenham suas proporções, fazendo com que seus documentos tenham uma aparência profissional e sofisticada. Sinta-se à vontade para experimentar diferentes imagens e formas para ver como o recurso de bloqueio de proporção funciona em vários cenários.

## Perguntas frequentes

### Posso desbloquear a proporção depois de bloqueá-la?
Sim, você pode desbloquear a proporção configurando`shape.AspectRatioLocked = false`.

### O que acontece se eu redimensionar uma imagem com proporção bloqueada?
A imagem será redimensionada proporcionalmente, mantendo a proporção original entre largura e altura.

### Posso aplicar isso a outras formas além de imagens?
Absolutamente! O recurso de bloqueio de proporção pode ser aplicado a qualquer forma, incluindo retângulos, círculos e muito mais.

### O Aspose.Words for .NET é compatível com o .NET Core?
Sim, Aspose.Words for .NET oferece suporte a .NET Framework e .NET Core.

### Onde posso encontrar mais documentação sobre Aspose.Words for .NET?
 Você pode encontrar documentação abrangente[aqui](https://reference.aspose.com/words/net/).