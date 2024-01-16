---
title: Anexar texto marcado em documento do Word
linktitle: Anexar texto marcado em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar texto de um marcador em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/append-bookmarked-text/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Append Bookmarked Text na biblioteca Aspose.Words for .NET. Este recurso permite adicionar o texto contido em um marcador específico de um documento do Word a outro documento.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: obter parágrafos do marcador

 Antes de começarmos a adicionar o texto do marcador, precisamos obter os parágrafos que contêm o início e o fim do marcador. Isso pode ser feito acessando o`BookmarkStart` e`BookmarkEnd` propriedades do marcador:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Etapa 2: verifique os parágrafos principais

Verificamos se os parágrafos iniciais e finais têm pais válidos, ou seja, se realmente pertencem a um parágrafo. Caso contrário, geramos uma exceção:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Etapa 3: verifique os pais dos parágrafos

Verificamos se os parágrafos inicial e final têm o mesmo pai. Caso contrário, isso significa que os parágrafos não estão contidos na mesma seção ou documento e estamos lançando uma exceção:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Etapa 4: copiar parágrafos

Iteramos pelos nós (parágrafos) do parágrafo inicial ao parágrafo final. Para cada nó, criamos uma cópia e a importamos para o contexto do documento de destino:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Exemplo de código-fonte para acrescentar texto marcado como favorito usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar a adição de texto de um marcador usando Aspose.Words for .NET:

```csharp

	// Este é o parágrafo que contém o início do marcador.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Este é o parágrafo que contém o final do marcador.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Limitamo-nos a um cenário razoavelmente simples.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Queremos copiar todos os parágrafos desde o parágrafo inicial até (e incluindo) o parágrafo final,
	// portanto, o nó no qual paramos é aquele após o parágrafo final.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//Isso cria uma cópia do nó atual e o importa (torna-o válido) no contexto
		// do documento de destino. Importar significa ajustar estilos e identificadores de lista corretamente.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar a função Append Bookmarked Text do Aspose.Words for .NET. Seguimos um guia passo a passo para obter parágrafos de um marcador, verificar os pais e copiar parágrafos para outro documento.

### Perguntas frequentes sobre como anexar texto marcado em um documento do Word

#### Q1: Quais são os pré-requisitos para usar o recurso "Adicionar texto com marcadores" no Aspose.Words for .NET?

R: Para usar a função "Adicionar texto com marcadores" no Aspose.Words for .NET, você precisa ter conhecimento básico da linguagem C#. Você também precisa de um ambiente de desenvolvimento .NET com a biblioteca Aspose.Words instalada.

#### Q2: Como obter os parágrafos que contêm o início e o fim de um marcador em um documento do Word?

R: Para obter os parágrafos que contêm o início e o fim de um marcador em um documento do Word, você pode acessar o`BookmarkStart` e`BookmarkEnd` propriedades do marcador. Aqui está um exemplo de código:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3: O que acontece se os parágrafos inicial e final não tiverem pais válidos?

R: Se os parágrafos inicial e final não tiverem pais válidos, ou seja, não forem realmente parágrafos, uma exceção será lançada. Esta situação não pode ser gerida neste momento.
