---
title: Mesclagem horizontal
linktitle: Mesclagem horizontal
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como mesclar células horizontalmente em um documento do Word usando Aspose.Words for .NET com este tutorial passo a passo detalhado.
type: docs
weight: 10
url: /pt/net/programming-with-tables/horizontal-merge/
---
## Introdução

Ei! Pronto para mergulhar no mundo do Aspose.Words for .NET? Hoje vamos abordar um recurso super útil: mesclagem horizontal em tabelas. Isso pode parecer um pouco técnico, mas não se preocupe, eu estou te protegendo. Ao final deste tutorial, você será um profissional em mesclar células em seus documentos do Word de forma programática. Então, vamos arregaçar as mangas e começar!

## Pré-requisitos

Antes de entrarmos no âmago da questão, há algumas coisas que você precisa ter em mente:

1. Biblioteca Aspose.Words for .NET: Se ainda não o fez, baixe a biblioteca Aspose.Words for .NET. Você pode agarrá-lo[aqui](https://releases.aspose.com/words/net/).
2. Ambiente de desenvolvimento: certifique-se de ter um ambiente de desenvolvimento adequado configurado, como o Visual Studio.
3. Conhecimento básico de C#: Um conhecimento básico de programação C# será benéfico.

Depois de classificá-los, você estará pronto para começar!

## Importar namespaces

Antes de mergulhar no código, vamos garantir que importamos os namespaces necessários. Em seu projeto C#, certifique-se de incluir:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Tudo bem, vamos analisar o processo de mesclagem horizontal de células de tabela em um documento do Word usando Aspose.Words for .NET.

## Etapa 1: configurando seu documento

 Primeiramente, precisamos criar um novo documento do Word e inicializar o`DocumentBuilder`:

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Este trecho de código configura um novo documento e prepara o`DocumentBuilder` para a ação.

## Passo 2: Inserindo a Primeira Célula

A seguir, começamos inserindo a primeira célula e marcando-a para mesclagem horizontal:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
```

 Aqui, inserimos uma nova célula e definimos seu`HorizontalMerge`propriedade para`CellMerge.First`, indicando que esta célula é o início de uma sequência de células mescladas.

## Etapa 3: Inserindo a célula mesclada

Agora, inserimos a célula que será mesclada com a anterior:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
builder.EndRow();
```

 Esta célula está configurada para se fundir com a célula anterior usando`CellMerge.Previous` . Observe como terminamos a linha com`builder.EndRow()`.

## Etapa 4: Inserindo células não mescladas

Para ilustrar a diferença, vamos inserir algumas células não mescladas:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in one cell.");
builder.InsertCell();
builder.Write("Text in another cell.");
builder.EndRow();
```

Aqui, inserimos duas células sem mesclagem horizontal. Isso mostra como as células se comportam quando não fazem parte de uma sequência mesclada.

## Etapa 5: finalizando a mesa

Por fim, finalizamos a tabela e salvamos o documento:

```csharp
builder.EndTable();
doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

Este trecho de código completa a tabela e salva o documento no diretório especificado.

## Conclusão

E aí está! Você acabou de dominar a arte de mesclar células horizontalmente em um documento do Word usando Aspose.Words for .NET. Seguindo essas etapas, você pode criar estruturas de tabelas complexas com facilidade. Continue experimentando e explorando os recursos do Aspose.Words para tornar seus documentos tão dinâmicos e flexíveis quanto você precisa. Boa codificação!

## Perguntas frequentes

### O que é Aspose.Words para .NET?
Aspose.Words for .NET é uma biblioteca poderosa que permite aos desenvolvedores criar, editar e manipular documentos do Word programaticamente em aplicativos .NET.

### Posso mesclar células verticalmente com Aspose.Words for .NET?
 Sim, você também pode mesclar células verticalmente usando o`CellFormat.VerticalMerge` propriedade.

### O uso do Aspose.Words for .NET é gratuito?
 Aspose.Words for .NET oferece uma avaliação gratuita, mas para funcionalidade completa, você precisará adquirir uma licença. Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### Como posso aprender mais sobre o Aspose.Words para .NET?
 Você pode explorar a documentação detalhada[aqui](https://reference.aspose.com/words/net/).

### Onde posso obter suporte para Aspose.Words for .NET?
 Para qualquer dúvida ou problema, você pode visitar o fórum de suporte Aspose[aqui](https://forum.aspose.com/c/words/8).