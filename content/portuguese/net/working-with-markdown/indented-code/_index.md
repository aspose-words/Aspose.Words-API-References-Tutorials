---
title: Código recuado
linktitle: Código recuado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar código recuado com o guia passo a passo Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/indented-code/
---

Neste exemplo, explicaremos como usar o recurso de código recuado com Aspose.Words for .NET. O código recuado é usado para representar visualmente blocos de código com formatação específica.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: adicionar estilo ao código recuado

Adicionaremos um estilo personalizado para o código recuado usando o`Styles.Add` método do`Document` objeto. Neste exemplo, estamos criando um estilo chamado “IndentedCode” para código recuado.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Etapa 3: adicionar código recuado

Agora podemos adicionar um bloco de código recuado usando o estilo personalizado "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### Exemplo de código-fonte para código recuado com Aspose.Words for .NET

```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Parabéns! Agora você aprendeu como usar o recurso de código recuado com Aspose.Words for .NET.


### Perguntas frequentes

#### P: O que é código recuado no Markdown?

R: O código recuado no Markdown é um método de formatação usado para exibir o código em um documento Markdown. Consiste em recuar cada linha de código com espaços ou tabulações.

#### P: Como usar código recuado no Markdown?

R: Para usar código recuado no Markdown, recue cada linha de código com espaços ou tabulações.

#### P: Quais são as vantagens do código recuado no Markdown?

R: O código recuado no Markdown melhora a legibilidade do código e facilita a compreensão dos leitores.

#### P: Qual é a diferença entre código recuado e blocos de código no Markdown?

R: O código recuado é usado para pequenos trechos de código inseridos no texto, enquanto os blocos de código são usados para exibir trechos maiores de código em formatação separada.

#### P: O código recuado no Markdown é compatível com todos os editores do Markdown?

R: O suporte para código recuado no Markdown pode variar entre os editores do Markdown. Verifique a documentação específica do seu editor para ter certeza.