---
title: Exportar para Markdown com alinhamento de conteúdo de tabela
linktitle: Exportar para Markdown com alinhamento de conteúdo de tabela
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como exportar documentos do Word para Markdown com tabelas alinhadas usando Aspose.Words for .NET. Siga nosso guia passo a passo para tabelas Markdown perfeitas.
type: docs
weight: 10
url: /pt/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
## Introdução

Ei! Já se perguntou como exportar seu documento Word para o formato Markdown com tabelas perfeitamente alinhadas? Quer você seja um desenvolvedor trabalhando em documentação ou apenas alguém que adora Markdown, este guia é para você. Estaremos mergulhando nos detalhes do uso do Aspose.Words for .NET para conseguir isso. Pronto para transformar suas tabelas do Word em tabelas Markdown perfeitamente alinhadas? Vamos começar!

## Pré-requisitos

Antes de mergulharmos no código, há algumas coisas que você precisa ter em mente:

1.  Biblioteca Aspose.Words for .NET: Certifique-se de ter a biblioteca Aspose.Words for .NET. Você pode baixá-lo no[Página de lançamentos do Aspose](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: configure seu ambiente de desenvolvimento. Visual Studio é uma escolha popular para desenvolvimento .NET.
3. Conhecimento básico de C#: Compreender C# é essencial, pois escreveremos código nesta linguagem.
4. Exemplo de documento do Word: tenha um documento do Word que você possa usar para testes.

## Importar namespaces

Antes de começarmos a codificar, vamos importar os namespaces necessários. Isso nos dará acesso às classes e métodos Aspose.Words que usaremos.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Etapa 1: inicializar o documento e o DocumentBuilder

Primeiramente, precisamos criar um novo documento do Word e inicializar um`DocumentBuilder` objeto para começar a construir nosso documento.

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Crie um novo documento.
Document doc = new Document();

// Inicialize o DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: inserir células e alinhar conteúdo

A seguir, inseriremos algumas células em nosso documento e definiremos seu alinhamento. Isto é crucial para garantir que a exportação Markdown mantenha o alinhamento correto.

```csharp
// Insira uma célula e defina o alinhamento à direita.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");

// Insira outra célula e defina o alinhamento ao centro.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

## Etapa 3: definir o alinhamento do conteúdo da tabela para exportação de markdown

 Agora é hora de configurar o`MarkdownSaveOptions` para controlar o alinhamento do conteúdo da tabela no arquivo Markdown exportado. Salvaremos o documento com diferentes configurações de alinhamento para ver como funciona.

```csharp
// Crie o objeto MarkdownSaveOptions.
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    TableContentAlignment = TableContentAlignment.Left
};

// Salve o documento com alinhamento à esquerda.
doc.Save(dataDir + "LeftTableContentAlignment.md", saveOptions);

// Mude o alinhamento para a direita e salve.
saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "RightTableContentAlignment.md", saveOptions);

// Mude o alinhamento para centralizar e salve.
saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "CenterTableContentAlignment.md", saveOptions);
```

## Etapa 4: use o alinhamento automático do conteúdo da tabela

 O`Auto` opção de alinhamento obtém o alinhamento do primeiro parágrafo na coluna da tabela correspondente. Isso pode ser útil quando você mistura alinhamentos em uma única tabela.

```csharp
// Defina o alinhamento como Automático.
saveOptions.TableContentAlignment = TableContentAlignment.Auto;

// Salve o documento com alinhamento automático.
doc.Save(dataDir + "AutoTableContentAlignment.md", saveOptions);
```

## Conclusão

E aí está! Exportar documentos do Word para Markdown com tabelas alinhadas usando Aspose.Words for .NET é muito fácil quando você sabe como fazê-lo. Esta poderosa biblioteca facilita o controle da formatação e do alinhamento de suas tabelas, garantindo que seus documentos Markdown tenham a aparência que você deseja. Boa codificação!

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, modificar, converter e exportar documentos do Word programaticamente.

### Posso definir alinhamentos diferentes para colunas diferentes na mesma tabela?
 Sim, usando o`Auto` opção de alinhamento, você pode ter alinhamentos diferentes com base no primeiro parágrafo de cada coluna.

### Preciso de uma licença para usar o Aspose.Words for .NET?
 Sim, Aspose.Words for .NET requer uma licença para funcionalidade completa. Você pode obter um[licença temporária](https://purchase.aspose.com/temporary-license/) para avaliação.

### É possível exportar outros elementos do documento para Markdown usando Aspose.Words?
Sim, Aspose.Words suporta a exportação de vários elementos como títulos, listas e imagens para o formato Markdown.

### Onde posso obter suporte se tiver problemas?
 Você pode obter suporte do[Fórum de suporte Aspose.Words](https://forum.aspose.com/c/words/8).
