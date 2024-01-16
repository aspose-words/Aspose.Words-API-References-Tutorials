---
title: Granularidade de comparação em documento do Word
linktitle: Granularidade de comparação em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda a comparar granularidade no recurso de documento do Word do Aspose.Words for .NET que permite que documentos sejam comparados caractere por caractere, relatando as alterações feitas.
type: docs
weight: 10
url: /pt/net/compare-documents/comparison-granularity/
---
Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso Comparar granularidade em documento do Word do Aspose.Words for .NET.

## Etapa 1: introdução

O recurso Compare Granularity do Aspose.Words for .NET permite comparar documentos no nível do caractere. Isso significa que cada caractere será comparado e as alterações serão relatadas de acordo.

## Passo 2: Configurando o ambiente

Antes de começar, você precisa configurar seu ambiente de desenvolvimento para funcionar com Aspose.Words for .NET. Certifique-se de ter a biblioteca Aspose.Words instalada e um projeto C# adequado para incorporar o código.

## Etapa 3: adicionar montagens necessárias

Para usar o recurso Compare Granularity do Aspose.Words for .NET, você precisa adicionar os assemblies necessários ao seu projeto. Certifique-se de ter as referências adequadas ao Aspose.Words em seu projeto.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Etapa 4: Criação de Documentos

Nesta etapa, criaremos dois documentos utilizando a classe DocumentBuilder. Esses documentos serão usados para a comparação.

```csharp
// Crie o documento A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Crie o documento B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Etapa 5: configurando opções de comparação

Nesta etapa, configuraremos as opções de comparação para especificar a granularidade da comparação. Aqui usaremos granularidade em nível de caractere.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Etapa 6: comparação de documentos

Agora vamos comparar os documentos usando o método Compare da classe Document. As alterações serão salvas no documento A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 O`Compare` O método compara o documento A com o documento B e salva as alterações no documento A. Você pode especificar o nome do autor e a data de comparação para referência.

## Conclusão

Neste artigo, exploramos o recurso Compare Granularity do Aspose.Words for .NET. Este recurso permite comparar documentos no nível do personagem e relatar alterações. Você pode usar esse conhecimento para realizar comparações detalhadas de documentos em seus projetos.

### Exemplo de código-fonte para granularidade de comparação usando Aspose.Words for .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## Conclusão

Neste tutorial, exploramos o recurso Comparison Granularity do Aspose.Words for .NET. Este recurso permite especificar o nível de detalhe ao comparar documentos. Ao escolher diferentes níveis de granularidade, você pode realizar comparações detalhadas em nível de caractere, palavra ou bloco, dependendo de seus requisitos específicos. Aspose.Words for .NET fornece um recurso de comparação de documentos flexível e poderoso, facilitando a identificação de diferenças em documentos com vários níveis de granularidade.

### Perguntas frequentes

#### P: Qual é o propósito de usar granularidade de comparação no Aspose.Words for .NET?

R: A granularidade da comparação no Aspose.Words for .NET permite que você especifique o nível de detalhe ao comparar documentos. Com esse recurso, você pode comparar documentos em diferentes níveis, como nível de caractere, nível de palavra ou até mesmo nível de bloco. Cada nível de granularidade fornece um nível diferente de detalhe nos resultados da comparação.

#### P: Como uso a granularidade de comparação no Aspose.Words for .NET?

R: Para usar a granularidade de comparação no Aspose.Words for .NET, siga estas etapas:
1. Configure seu ambiente de desenvolvimento com a biblioteca Aspose.Words.
2. Adicione os assemblies necessários ao seu projeto referenciando Aspose.Words.
3.  Crie os documentos que deseja comparar usando o`DocumentBuilder` aula.
4.  Configure as opções de comparação criando um`CompareOptions` objeto e definir o`Granularity` propriedade para o nível desejado (por exemplo,`Granularity.CharLevel` para comparação em nível de personagem).
5.  Use o`Compare` método em um documento, passando o outro documento e o`CompareOptions` objeto como parâmetros. Este método irá comparar os documentos com base na granularidade especificada e salvar as alterações no primeiro documento.

#### P: Quais são os níveis disponíveis de granularidade de comparação no Aspose.Words for .NET?

R: Aspose.Words for .NET oferece três níveis de granularidade de comparação:
- `Granularity.CharLevel`: compara documentos no nível do personagem.
- `Granularity.WordLevel`: compara documentos no nível da palavra.
- `Granularity.BlockLevel`: compara documentos no nível do bloco.

#### P: Como posso interpretar os resultados da comparação com granularidade em nível de caractere?

R: Com granularidade em nível de caractere, cada caractere nos documentos comparados é analisado em busca de diferenças. Os resultados da comparação mostrarão mudanças no nível de personagem individual, incluindo adições, exclusões e modificações.