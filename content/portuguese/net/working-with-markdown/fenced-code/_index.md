---
title: Código Cercado
linktitle: Código Cercado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar o recurso de código protegido com o guia passo a passo do Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/fenced-code/
---

Neste exemplo, orientaremos você sobre como usar o recurso de código protegido com Aspose.Words for .NET. código protegido é usado para representar blocos de código com formatação específica.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: Adicionando um estilo para código protegido

 Adicionaremos um estilo personalizado para o código protegido usando o`Styles.Add` método do`Document` objeto. Neste exemplo, estamos criando um estilo chamado "FencedCode" para o código protegido.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Etapa 3: Adicionar código protegido sem informações

Agora podemos adicionar um bloco de código protegido sem nenhuma sequência de informações usando o estilo personalizado "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## Etapa 4: adicionar código protegido com sequência de informações

Também podemos adicionar um bloco de código protegido com uma sequência de informações usando outro estilo personalizado. Neste exemplo, estamos criando um estilo chamado "FencedCode.C#" para representar um bloco de código C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Exemplo de código-fonte para Fenced Code usando Aspose.Words for .NET

```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Perguntas frequentes

#### P: O que é código delimitado no Markdown?

R: O código delimitado no Markdown é um método de formatação usado para exibir o código em um documento Markdown. Consiste em enquadrar o código com delimitadores específicos.

#### P: Quais são os benefícios do código delimitado no Markdown?

R: O código delimitado no Markdown melhora a legibilidade do código e facilita a compreensão dos leitores. Também permite preservar o realce de sintaxe em alguns editores Markdown.

#### P: Qual é a diferença entre código delimitado e recuado no Markdown?

R: O código delimitado usa delimitadores específicos para delimitar o código, enquanto o código recuado envolve o recuo de cada linha de código com espaços ou tabulações.

#### P: O código delimitado no Markdown é compatível com todos os editores do Markdown?

R: O suporte para código delimitado no Markdown pode variar entre os editores do Markdown. Verifique a documentação específica do seu editor para ter certeza.

