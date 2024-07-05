---
title: Desembaraçar em documento Word
linktitle: Desembaraçar em documento Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como desembaraçar marcadores aninhados em documentos do Word em linhas adjacentes da tabela usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/untangle/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Untangle na biblioteca Aspose.Words for .NET. Esta função desvenda marcadores aninhados que estão em linhas adjacentes da tabela.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: navegar pelos favoritos do documento

Usamos um loop foreach para percorrer todos os marcadores presentes no documento:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Código para lidar com marcadores aqui
}
```

## Etapa 2: obter linhas principais dos favoritos

 Nós usamos o`GetAncestor` métodos para recuperar as linhas pai dos nós inicial e final do marcador:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Etapa 3: desembaraçar marcadores aninhados

Se ambas as linhas principais forem encontradas e o marcador começar e terminar em linhas adjacentes, moveremos o nó final do marcador para o final do último parágrafo da última célula na linha superior:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Exemplo de código-fonte para Untangle usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para desembaraçar marcadores aninhados usando Aspose.Words for .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Obtenha a linha pai do marcador e do nó final do marcador.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Se ambas as linhas forem encontradas corretamente e o início e o fim do marcador estiverem contidos em linhas adjacentes,
		// mova o nó final do marcador para o final do último parágrafo na última célula da linha superior.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar a função Untangle do Aspose.Words for .NET. Seguimos um guia passo a passo para desembaraçar marcadores aninhados em linhas adjacentes da tabela.

### Perguntas frequentes

#### P: A função Untangle funciona apenas com marcadores aninhados em linhas adjacentes da tabela?

R: Sim, o recurso Untangle foi projetado especificamente para desembaraçar marcadores aninhados que estão em linhas adjacentes da tabela. Se os marcadores não estiverem em linhas adjacentes, esta função não será aplicável.

#### P: Como posso identificar marcadores aninhados em meu documento do Word?

R: Você pode identificar marcadores aninhados percorrendo os marcadores no documento e verificando se o marcador inicial e o marcador final estão em linhas adjacentes da tabela. Você pode usar o código-fonte fornecido neste artigo como ponto de partida para implementar essa funcionalidade.

#### P: A função Unscramble modifica o conteúdo do documento original?

R: Sim, a função Untangle modifica o documento original movendo o nó final do marcador para o final do último parágrafo da última célula da linha superior. Certifique-se de salvar uma cópia de backup do documento antes de aplicar este recurso.

#### P: Como posso desembaraçar marcadores aninhados em outros tipos de elementos de documento, como seções ou parágrafos?

R: A função Untangle apresentada neste artigo foi projetada especificamente para desembaraçar marcadores aninhados em linhas adjacentes da tabela. Se quiser desemaranhar marcadores aninhados em outros elementos do documento, você precisará adaptar o código adequadamente e usar métodos apropriados para acessar os elementos desejados.

#### P: Existem outros métodos para desembaraçar marcadores aninhados em um documento do Word usando Aspose.Words for .NET?

 R: O método apresentado neste artigo é um método comum para desemaranhar marcadores aninhados em linhas adjacentes da tabela. No entanto, podem existir outras abordagens ou técnicas dependendo das necessidades específicas do seu projeto. Você pode conferir o[Referências de API Aspose.Words para .NET](https://reference.aspose.com/words/net/) para explorar ainda mais os recursos disponíveis.