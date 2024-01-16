---
title: Excluir linha por marcador em documento do Word
linktitle: Excluir linha por marcador em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como excluir uma linha da tabela com base em um marcador específico em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/delete-row-by-bookmark/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Excluir linha por marcador na biblioteca Aspose.Words for .NET. Este recurso permite excluir uma linha da tabela com base em um marcador específico no documento do Word.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Passo 1: Obtendo o marcador

 Nós usamos o`Bookmarks` propriedade do intervalo do documento para obter o marcador específico que queremos usar para excluir a linha da tabela:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Etapa 2: excluir a linha da tabela

 Nós usamos o`GetAncestor` método para obter o`Row` digite o elemento pai do marcador. A seguir, usamos o`Remove` método para remover a linha da tabela:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Exemplo de código-fonte para Excluir linha por marcador usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar a exclusão de uma linha da tabela com base em um marcador específico usando Aspose.Words for .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar a função Excluir linha por marcador do Aspose.Words for .NET. Seguimos um guia passo a passo para excluir uma linha da tabela com base em um marcador específico em um documento.

### Perguntas frequentes para excluir linha por marcador em documento do Word

#### P: Posso excluir várias linhas usando o mesmo marcador?

R: Sim, você pode excluir várias linhas usando o mesmo marcador. No entanto, você precisa lidar com a lógica do seu código para determinar o número de linhas a serem excluídas e fazer os ajustes necessários no snippet de código fornecido.

#### P: O que acontece se o marcador não existir no documento?

R: Se o marcador especificado não existir no documento, o trecho de código retornará um valor nulo para o objeto marcador. Portanto, você precisa lidar com esse cenário em seu código adicionando verificações apropriadas antes de tentar excluir a linha da tabela.

#### P: O uso da biblioteca Aspose.Words é gratuito?

 R: A biblioteca Aspose.Words é uma biblioteca comercial e você pode exigir uma licença válida para usá-la em seus projetos. Você pode visitar o[Referências de API Aspose.Words para .NET](https://reference.aspose.com/words/net/) para saber mais sobre suas opções de licenciamento e preços.

#### P: Posso excluir linhas de uma tabela em uma seção específica do documento do Word?

R: Sim, você pode excluir linhas de uma tabela em uma seção específica de um documento do Word. Você pode modificar o snippet de código fornecido para direcionar uma seção específica usando o intervalo ou marcador apropriado dentro dessa seção.