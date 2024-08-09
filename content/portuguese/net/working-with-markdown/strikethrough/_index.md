---
title: Tachado
linktitle: Tachado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como aplicar formatação tachado ao texto usando Aspose.Words for .NET com nosso guia passo a passo. Aprimore suas habilidades de processamento de documentos.
type: docs
weight: 10
url: /pt/net/working-with-markdown/strikethrough/
---
## Introdução

Bem-vindo a este guia detalhado sobre como aplicar formatação tachado a texto usando Aspose.Words for .NET. Se você deseja aprimorar suas habilidades de processamento de documentos e adicionar um toque exclusivo ao seu texto, você está no lugar certo. Vamos mergulhar!

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:

-  Aspose.Words para .NET: Faça o download[aqui](https://releases.aspose.com/words/net/).
- .NET Framework: Certifique-se de ter o .NET Framework instalado em seu sistema.
- Ambiente de desenvolvimento: um IDE como o Visual Studio.
- Conhecimento básico de C#: É necessária familiaridade com programação C#.

## Importar namespaces

Para começar, você precisará importar os namespaces necessários. Eles são essenciais para acessar a biblioteca Aspose.Words e seus recursos.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: inicializar o DocumentBuilder

 O`DocumentBuilder` class é uma ferramenta poderosa do Aspose.Words que permite adicionar conteúdo ao seu documento com facilidade.

```csharp
// Inicialize um DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: definir a propriedade tachado

Agora, vamos aplicar a propriedade tachado ao nosso texto. Isto envolve definir o`StrikeThrough` propriedade do`Font` opor-se a`true`.

```csharp
// Faça o texto tachado.
builder.Font.StrikeThrough = true;
```

## Etapa 3: escrever texto tachado

 Com a propriedade tachado definida, agora podemos adicionar nosso texto. O`Writeln` método irá adicionar o texto ao documento.

```csharp
// Escreva o texto com Tachado.
builder.Writeln("This text will be StrikeThrough");
```

## Conclusão

E aí está! Você adicionou com sucesso a formatação tachada ao seu texto usando Aspose.Words for .NET. Esta poderosa biblioteca abre um mundo de possibilidades para processamento e personalização de documentos. Esteja você criando relatórios, cartas ou qualquer outro tipo de documento, dominar esses recursos sem dúvida aumentará sua produtividade e a qualidade de seus resultados.

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma poderosa biblioteca de processamento de documentos que permite aos desenvolvedores criar, manipular e converter documentos do Word programaticamente.

### Posso usar o Aspose.Words for .NET em um projeto comercial?
 Sim, você pode usar Aspose.Words for .NET em projetos comerciais. Para opções de compra, visite o[página de compra](https://purchase.aspose.com/buy).

### Existe um teste gratuito disponível para Aspose.Words for .NET?
 Sim, você pode baixar uma versão de teste gratuita[aqui](https://releases.aspose.com/).

### Como obtenho suporte para Aspose.Words for .NET?
Você pode obter suporte da comunidade Aspose e de especialistas no[fórum de suporte](https://forum.aspose.com/c/words/8).

### Posso aplicar outras opções de formatação de texto usando Aspose.Words for .NET?
Absolutamente! Aspose.Words for .NET oferece suporte a uma ampla variedade de opções de formatação de texto, incluindo negrito, itálico, sublinhado e muito mais.