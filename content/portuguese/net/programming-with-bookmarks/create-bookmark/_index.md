---
title: Criar marcador em documento do Word
linktitle: Criar marcador em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar marcadores em documentos do Word usando Aspose.Words for .NET com este guia passo a passo detalhado. Perfeito para navegação e organização de documentos.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/create-bookmark/
---
## Introdução

Criar marcadores em um documento do Word pode mudar o jogo, especialmente quando você deseja navegar facilmente por documentos grandes. Hoje, percorreremos o processo de criação de marcadores usando Aspose.Words for .NET. Este tutorial irá guiá-lo passo a passo, garantindo que você entenda cada parte do processo. Então, vamos mergulhar de cabeça!

## Pré-requisitos

Antes de começarmos, você precisa ter o seguinte:

1.  Biblioteca Aspose.Words for .NET: Baixe e instale em[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de Desenvolvimento: Visual Studio ou qualquer outro ambiente de desenvolvimento .NET.
3. Conhecimento básico de C#: Compreensão dos conceitos básicos de programação em C#.

## Importar namespaces

Para trabalhar com Aspose.Words for .NET, você precisa importar os namespaces necessários:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: configurar o documento e o DocumentBuilder

Inicialize o documento

Primeiro, precisamos criar um novo documento e inicializar o`DocumentBuilder`. Este é o ponto de partida para adicionar conteúdo e marcadores ao seu documento.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Explicação: O`Document` objeto é sua tela. O`DocumentBuilder` é como sua caneta, que permite escrever conteúdo e criar marcadores no documento.

## Etapa 2: crie o marcador principal

Iniciar e terminar o marcador principal

Para criar um marcador, você precisa especificar os pontos inicial e final. Aqui, criaremos um marcador chamado “Meu marcador”.

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");
```

 Explicação: O`StartBookmark` método marca o início do marcador e`Writeln` adiciona texto ao marcador.

## Etapa 3: crie um marcador aninhado

Adicionar marcador aninhado dentro do marcador principal

Você pode aninhar marcadores dentro de outros marcadores. Aqui, adicionamos "Nested Bookmark" em "My Bookmark".

```csharp
builder.StartBookmark("Nested Bookmark");
builder.Writeln("Text inside a NestedBookmark.");
builder.EndBookmark("Nested Bookmark");
```

 Explicação: O aninhamento de marcadores permite uma organização de conteúdo mais estruturada e hierárquica. O`EndBookmark` método fecha o marcador atual.

## Etapa 4: adicionar texto fora do marcador aninhado

Continuar adicionando conteúdo

Após o marcador aninhado, podemos continuar adicionando mais conteúdo ao marcador principal.

```csharp
builder.Writeln("Text after Nested Bookmark.");
builder.EndBookmark("My Bookmark");
```

Explicação: Isso garante que o marcador principal inclua tanto o marcador aninhado quanto o texto adicional.

## Passo 5: Configurar opções para salvar PDF

Configurar opções de salvamento de PDF para marcadores

Ao salvar o documento como PDF, podemos configurar opções para incluir marcadores.

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);
```

 Explicação: O`PdfSaveOptions` class permite que você especifique como o documento deve ser salvo como PDF. O`BookmarksOutlineLevels` propriedade define a hierarquia dos marcadores no PDF.

## Etapa 6: salve o documento

Salve o documento como PDF

Finalmente, salve o documento com as opções especificadas.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

 Explicação: O`Save` método salva o documento no formato e local especificados. O PDF agora incluirá os marcadores que criamos.

## Conclusão

Criar marcadores em um documento do Word usando Aspose.Words for .NET é simples e imensamente útil para navegação e organização de documentos. Esteja você gerando relatórios, criando e-books ou gerenciando documentos grandes, os marcadores facilitam sua vida. Siga as etapas descritas neste tutorial e você terá um PDF marcado pronto rapidamente.

## Perguntas frequentes

### Posso criar vários marcadores em níveis diferentes?

Absolutamente! Você pode criar quantos marcadores forem necessários e definir seus níveis hierárquicos ao salvar o documento como PDF.

### Como atualizo o texto de um marcador?

 Você pode navegar até o marcador usando`DocumentBuilder.MoveToBookmark` e atualize o texto.

### É possível excluir um favorito?

 Sim, você pode excluir um favorito usando o`Bookmarks.Remove` método especificando o nome do marcador.

### Posso criar marcadores em outros formatos além de PDF?

Sim, Aspose.Words oferece suporte a marcadores em vários formatos, incluindo DOCX, HTML e EPUB.

### Como posso garantir que os marcadores apareçam corretamente no PDF?

 Certifique-se de definir o`BookmarksOutlineLevels` corretamente no`PdfSaveOptions`. Isso garante que os marcadores sejam incluídos no esboço do PDF.