---
title: Ênfases
linktitle: Ênfases
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar ênfases (negrito e itálico) com o guia passo a passo Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/emphases/
---

Neste exemplo, explicaremos como usar ênfases com Aspose.Words for .NET. ênfases são usadas para enfatizar certas partes do texto, como negrito e itálico.

## Etapa 1: inicialização do documento

 Primeiro, inicializaremos o documento criando uma instância do`Document` aula.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Etapa 2: usando um gerador de documentos

seguir, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: adicione texto com ênfase

Podemos adicionar texto de ênfase alterando as propriedades de fonte do gerador de documentos. Neste exemplo, usamos negrito e itálico para enfatizar diferentes partes do texto.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Passo 4: Salvando o documento

 Finalmente, podemos salvar o documento no formato desejado. Neste exemplo, estamos usando o`.md` extensão para um formato Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Parabéns! Agora você aprendeu como usar ênfases com Aspose.Words for .NET.

### Exemplo de código-fonte para Emphases usando Aspose.Words for .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### Perguntas frequentes

#### P: Como realço texto usando Markdown?

 R: Para destacar texto usando Markdown, simplesmente coloque o texto entre os símbolos apropriados. Usar`*` ou`_` para itálico,`**` ou`__` para ousado e`~~` para tachado.

#### P: Podemos combinar diferentes destaques no mesmo texto?

 R: Sim, é possível combinar diferentes destaques no mesmo texto. Por exemplo, você pode colocar uma palavra em negrito e itálico usando ambos`**` e`*`ao redor do mundo.

#### P: Quais opções de destaque estão disponíveis no Markdown?

R: As opções de destaque disponíveis no Markdown são itálico (`*` ou`_`), audacioso (`**` ou`__`) e tachado (`~~`).

#### P: Como faço para lidar com casos em que o texto contém caracteres especiais usados pelo Markdown para realçar?

 R: Se o seu texto contém caracteres especiais usados pelo Markdown para realçar, você pode escapá-los precedendo-os com um`\` . Por exemplo,`\*` exibirá um asterisco literal.

#### P: Podemos personalizar a aparência do destaque usando CSS?

R: O realce no Markdown geralmente é renderizado usando os estilos padrão do navegador. Se você converter seu Markdown para HTML, poderá personalizar a aparência do destaque usando regras CSS.