---
title: Código Cercado
linktitle: Código Cercado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar código protegido e strings de informações a documentos do Word usando Aspose.Words for .NET. Guia passo a passo incluído. Aprimore suas habilidades de formatação de documentos.
type: docs
weight: 10
url: /pt/net/working-with-markdown/fenced-code/
---
## Introdução

Olá, colega programador! Hoje, estamos mergulhando no mundo do Aspose.Words for .NET para dominar a arte de adicionar código protegido e código protegido com strings de informações aos seus documentos do Word. Imagine seu documento do Word como uma tela e você, o artista, está prestes a pintar com a precisão de um desenvolvedor experiente. Com Aspose.Words, você tem o poder de aprimorar programaticamente seus documentos com blocos de código estruturados e formatados, fazendo com que seus documentos técnicos brilhem com profissionalismo e clareza.

## Pré-requisitos

Antes de entrarmos no tutorial, vamos ter certeza de que você tem tudo o que precisa:

- Conhecimento básico de C#: uma compreensão geral de C# o ajudará a compreender os conceitos rapidamente.
-  Aspose.Words for .NET: Você precisa ter o Aspose.Words for .NET instalado. Se você ainda não tem, pegue[aqui](https://releases.aspose.com/words/net/).
- Ambiente de desenvolvimento: Visual Studio ou qualquer outro IDE C# com o qual você se sinta confortável.

## Importar namespaces

Em primeiro lugar, você precisa importar os namespaces necessários. É como reunir todas as suas ferramentas antes de iniciar um projeto.

```csharp
using Aspose.Words;
using Aspose.Words.Style;
```

Agora, vamos detalhar o processo passo a passo.

## Etapa 1: configurando seu projeto

Antes de podermos criar blocos de código bonitos e formatados em nosso documento do Word, precisamos configurar um novo projeto no Visual Studio.

1. Crie um novo projeto: abra o Visual Studio e crie um novo aplicativo de console C#.
2. Adicionar referência Aspose.Words: Instale Aspose.Words por meio do NuGet Package Manager. Você pode fazer isso clicando com o botão direito do mouse em seu projeto no Solution Explorer, selecionando "Gerenciar pacotes NuGet" e pesquisando por Aspose.Words.

## Etapa 2: inicializar o DocumentBuilder

Agora que seu projeto está configurado, vamos inicializar o DocumentBuilder, que será nossa principal ferramenta para adicionar conteúdo ao documento Word.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 3: Crie um estilo para código protegido

Para adicionar código protegido, primeiro precisamos criar um estilo. Pense nisso como definir o tema do nosso bloco de código.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
fencedCode.Font.Name = "Courier New";
fencedCode.Font.Size = 10;
fencedCode.ParagraphFormat.LeftIndent = 20;
fencedCode.ParagraphFormat.RightIndent = 20;
fencedCode.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Etapa 4: adicionar código protegido ao documento

Com nosso estilo pronto, podemos agora adicionar um bloco de código protegido ao documento.

```csharp
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is a fenced code block");
```

## Etapa 5: Crie um estilo para código protegido com string de informações

Às vezes, você pode querer especificar a linguagem de programação ou adicionar informações extras ao seu bloco de código. Vamos criar um estilo para isso.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
fencedCodeWithInfo.Font.Name = "Courier New";
fencedCodeWithInfo.Font.Size = 10;
fencedCodeWithInfo.ParagraphFormat.LeftIndent = 20;
fencedCodeWithInfo.ParagraphFormat.RightIndent = 20;
fencedCodeWithInfo.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Etapa 6: adicionar código protegido com string de informações ao documento

Agora, vamos adicionar um bloco de código protegido com uma string de informações para indicar que é um código C#.

```csharp
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code block with info string - C#");
```

## Conclusão

Parabéns! Você acabou de adicionar blocos de código protegido e código protegido com strings de informações aos seus documentos do Word usando Aspose.Words for .NET. Esta é apenas a ponta do iceberg. Com Aspose.Words, você pode automatizar e aprimorar o processamento de documentos a novos patamares. Continue explorando e boa codificação!

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, manipular e converter documentos do Word programaticamente.

### Posso usar Aspose.Words com outras linguagens de programação?
Aspose.Words oferece suporte principalmente a linguagens .NET, mas existem versões disponíveis para Java, Python e outras linguagens.

### O uso do Aspose.Words é gratuito?
 Aspose.Words é um produto comercial, mas você pode baixar uma versão de avaliação gratuita[aqui](https://releases.aspose.com/)para explorar suas características.

### Como posso obter suporte para Aspose.Words?
 Você pode obter suporte da comunidade e dos desenvolvedores do Aspose[aqui](https://forum.aspose.com/c/words/8).

### Que outros recursos o Aspose.Words oferece?
Aspose.Words oferece uma ampla gama de recursos, incluindo conversão de documentos, geração de documentos baseados em modelos, relatórios e muito mais.