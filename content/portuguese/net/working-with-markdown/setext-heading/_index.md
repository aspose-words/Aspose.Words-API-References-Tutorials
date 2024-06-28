---
title: Título Setex
linktitle: Título Setex
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar títulos Setext para formatar seus documentos com o guia passo a passo Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/setext-heading/
---

Neste tutorial, orientaremos você sobre como usar o recurso Setext Heading com Aspose.Words for .NET. Setext Heading é um método alternativo de formatação de títulos em documentos Markdown.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Etapa 2: usando o estilo de título Setext

Usaremos o estilo de parágrafo padrão "Título 1" para criar um título de nível 1 em nosso documento.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Etapa 3: redefinindo estilos

Redefinimos os estilos de fonte aplicados anteriormente para evitar qualquer combinação indesejada de estilos entre parágrafos.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Etapa 4: Personalizando os níveis de título do Setext

Podemos personalizar os níveis de título do Setext adicionando novos estilos de parágrafo com base nos estilos de título existentes. Neste exemplo, estamos criando um estilo "SetextHeading1" baseado no estilo "Título 1" para representar um título de nível 1 no formato Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Passo 5: Salvando o documento

Finalmente, podemos salvar o documento no formato desejado.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Exemplo de código-fonte para títulos Setext com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Use um construtor de documentos para adicionar conteúdo ao documento.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Redefina os estilos do parágrafo anterior para não combinar estilos entre parágrafos.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Redefina os estilos do parágrafo anterior para não combinar estilos entre parágrafos.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// O nível de título Setex será redefinido para 2 se o parágrafo base tiver um nível de título maior que 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### Perguntas frequentes

#### P: O que é um cabeçalho Setext Markdown?

R: Um cabeçalho Setext Markdown é uma forma alternativa de criar títulos em um documento Markdown. Ele usa caracteres de sublinhado (= ou -) para indicar diferentes níveis de títulos.

#### P: Como usar os cabeçalhos Setext Markdown?

R: Para usar títulos Setext Markdown, coloque sublinhados abaixo do texto do título. Use sinais de igual (=) para um cabeçalho de nível 1 e hífens (-) para um cabeçalho de nível 2.

#### P: Há alguma limitação no uso de cabeçalhos Setext Markdown?

R: Os títulos Setext Markdown têm limitações em termos de hierarquia de títulos e não são tão distintos visualmente quanto os títulos Markdown padrão.

#### P: Posso personalizar a aparência dos cabeçalhos Setext Markdown?

R: No Markdown padrão, não é possível personalizar a aparência dos cabeçalhos do Setext Markdown. Eles têm uma aparência predefinida com base nos caracteres de sublinhado usados.

#### P: Os cabeçalhos Setext Markdown são suportados por todos os editores Markdown?

R: O suporte para cabeçalhos Setext Markdown pode variar entre os editores Markdown. Verifique a documentação específica do seu editor para ter certeza.