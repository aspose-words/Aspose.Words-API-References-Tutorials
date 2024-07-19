---
title: Citar
linktitle: Citar
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar citações com o guia passo a passo do Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/quote/
---

Neste exemplo, explicaremos como usar o recurso de citação com Aspose.Words for .NET Quote são usados para destacar seções de texto, cercando-as com uma borda especial.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: usando o estilo de citação padrão

Usaremos o estilo de parágrafo padrão chamado “Citação” para aplicar a formatação de citação ao texto.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Etapa 3: Criando estilos para níveis aninhados

 Podemos criar estilos para níveis aninhados usando o`Styles.Add` método do`Document`objeto. Neste exemplo, estamos criando um estilo chamado "Quote1" para representar um nível de cotação aninhada.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Exemplo de código-fonte para citações com Aspose.Words for .NET


```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

// Por padrão, um documento armazena o estilo blockquote para o primeiro nível.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Crie estilos para níveis aninhados por meio de herança de estilo.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Parabéns! Agora você aprendeu como usar o recurso de citações com Aspose.Words for .NET.


### Perguntas frequentes

#### P: O que é uma citação no Markdown?

R: Uma citação no Markdown é uma forma de destacar passagens de texto de outras fontes ou de fazer referência a citações famosas.

#### P: Como usar aspas no Markdown?

R: Para usar uma citação no Markdown, coloque o texto da citação entre colchetes angulares (`>`). Cada linha da citação deve começar com uma divisa.

#### P: As cotações Markdown suportam atributos?

R: As citações Markdown não suportam atributos específicos. Eles são simplesmente destacados pela formatação do texto citado.

#### P: Você pode incorporar cotações no Markdown?

R: Sim, é possível aninhar cotações no Markdown adicionando um nível extra de colchetes angulares (`>`).