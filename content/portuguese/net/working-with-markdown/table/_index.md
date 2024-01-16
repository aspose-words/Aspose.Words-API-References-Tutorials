---
title: Mesa
linktitle: Mesa
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar uma tabela com o guia passo a passo do Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/table/
---


Neste exemplo, orientaremos você sobre como criar uma tabela usando Aspose.Words for .NET. Uma tabela é uma estrutura de dados que organiza as informações em linhas e colunas.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Etapa 2: adicionar células e dados

 Adicionaremos células e dados à nossa tabela usando o`InsertCell` método e o`Writeln` método do gerador de documentos.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Exemplo de código-fonte para criar uma tabela com Aspose.Words for .NET

```csharp
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

// Adicione a primeira linha.
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

// Adicione a segunda linha.
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

Parabéns! Agora você aprendeu como criar uma tabela com Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como faço para criar uma tabela no Markdown?

R: Para criar uma tabela no Markdown, use a sintaxe de pipes (`|`para delimitar células e travessões (`-`) para delimitar os cabeçalhos das tabelas.

#### P: Podemos personalizar a aparência de uma tabela no Markdown?

R: No Markdown padrão, as opções de personalização de tabelas são limitadas. No entanto, alguns editores Markdown permitem adicionar estilos CSS às tabelas para personalizar sua aparência.

#### P: Como mesclar células em uma tabela no Markdown?

R: A mesclagem de células em uma tabela no Markdown depende do editor Markdown usado. Alguns editores Markdown suportam a mesclagem de células usando uma sintaxe específica.

#### P: As tabelas no Markdown oferecem suporte ao estilo CSS?

R: No Markdown padrão, as tabelas não oferecem suporte direto para estilos CSS. No entanto, alguns editores Markdown permitem adicionar estilos CSS às tabelas para personalizar sua aparência.

#### P: Podemos adicionar links ou texto em formato embutido nas células de uma tabela no Markdown?

R: Sim, você pode adicionar links ou texto embutido às células da tabela no Markdown usando a sintaxe apropriada do Markdown.