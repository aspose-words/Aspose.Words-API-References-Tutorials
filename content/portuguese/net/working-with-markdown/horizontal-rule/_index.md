---
title: Regra horizontal
linktitle: Regra horizontal
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir uma regra horizontal com o guia passo a passo Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/horizontal-rule/
---

Neste exemplo, mostraremos como usar o recurso de regra horizontal com Aspose.Words for .NET. As regras horizontais são usadas para separar visualmente seções de um documento.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Passo 2: Inserindo uma régua horizontal

 Podemos inserir uma régua horizontal usando o`InsertHorizontalRule` método do gerador de documentos.

```csharp
builder. InsertHorizontalRule();
```

## Exemplo de código-fonte para regra horizontal com Aspose.Words for .NET

```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

// Insira a régua horizontal.
builder.InsertHorizontalRule();
```

Parabéns! Agora você aprendeu como usar o recurso de regra horizontal com Aspose.Words for .NET.


### Perguntas frequentes

#### P: Como faço para criar uma régua horizontal no Markdown?

R: Para criar uma régua horizontal no Markdown, você pode usar um dos seguintes símbolos em uma linha vazia: três asteriscos (\***), três travessões (\---), ou três sublinhados (\___).

#### P: Posso personalizar a aparência de uma régua horizontal no Markdown?

R: No Markdown padrão, não há como personalizar a aparência das réguas horizontais. No entanto, alguns editores e extensões avançados do Markdown oferecem recursos adicionais de personalização.

#### P: As réguas horizontais são suportadas por todos os editores Markdown?

R: Sim, os editores Markdown mais populares suportam réguas horizontais. No entanto, é sempre melhor verificar a documentação específica do seu fornecedor para ter certeza de que há suporte.

#### P: Que outros elementos posso criar no Markdown?

R: Além das réguas horizontais, você pode criar títulos, parágrafos, listas, links, imagens, tabelas e muito mais no Markdown.