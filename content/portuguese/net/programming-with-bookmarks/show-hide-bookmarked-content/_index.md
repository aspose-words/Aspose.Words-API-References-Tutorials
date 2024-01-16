---
title: Mostrar ocultar conteúdo marcado em documento do Word
linktitle: Mostrar ocultar conteúdo marcado em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como mostrar ou ocultar o conteúdo dos favoritos em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Show Hide Bookmarked Content na biblioteca Aspose.Words for .NET. Este recurso permite mostrar ou ocultar o conteúdo de um marcador em um documento do Word com base em uma condição específica ao mesclar dados.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Passo 1: Obtendo o marcador

 Nós usamos o`Bookmarks` propriedade do intervalo do documento para obter o marcador específico no qual queremos mostrar ou ocultar o conteúdo:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Etapa 2: Inserindo os campos de mesclagem

 Usamos um construtor de documentos`DocumentBuilder` para inserir os campos de mesclagem necessários. Esses campos de mesclagem definirão uma condição para mostrar ou ocultar o conteúdo do marcador, dependendo do valor do`showHide` variável:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Etapa 3: mover o conteúdo dos favoritos

Percorremos o conteúdo do marcador e o movemos para que apareça

isse antes do marcador. Isso controlará a exibição ou ocultação do conteúdo com base na condição especificada:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Etapa 4: mover o restante do conteúdo do marcador

Movemos o restante do conteúdo do marcador após o marcador, usando o nó final do marcador como ponto de inserção:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Etapa 5: realizando a mesclagem

 Nós usamos o`Execute` método do documento`s `Mala direta` object to execute the merge using the bookmark name and the value of the `variável showHide`:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Exemplo de código-fonte para Mostrar Ocultar Conteúdo Marcado usando Aspose.Words for .NET

Aqui está o exemplo completo de código-fonte para demonstrar a exibição ou ocultação do conteúdo dos marcadores usando Aspose.Words for .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{marcador MERGEFIELD}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar o recurso Mostrar ocultar conteúdo marcado como favorito do Aspose.Words for .NET. Seguimos um guia passo a passo para mostrar ou ocultar o conteúdo de um marcador com base em uma condição específica ao mesclar dados.

### Perguntas frequentes sobre mostrar ocultar conteúdo marcado em documentos do Word

#### P: Posso usar a mesma condição para vários marcadores no mesmo documento?

R: Sim, você pode usar a mesma condição para vários marcadores no mesmo documento. Basta repetir as etapas 2 a 5 para cada marcador, ajustando o nome do marcador e, opcionalmente, o valor do`showhide` variável conforme necessário.

#### P: Como posso adicionar mais condições para mostrar ou ocultar o conteúdo dos favoritos?

 R: Para adicionar mais condições, você pode usar operadores lógicos como`AND` e`OR` no código para inserir os campos de mesclagem na etapa 2. Edite a condição no código a seguir para adicionar condições adicionais:

```csharp
builder. Write("\" = \"true\" ");
```

#### P: Como posso excluir um marcador em um documento do Word usando Aspose.Words for .NET?

 R: Para remover um marcador em um documento do Word usando Aspose.Words for .NET, você pode usar o`Remove` método do`Bookmarks` coleção do intervalo de documentos. Aqui está um exemplo de código para excluir um marcador específico:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### P: A biblioteca Aspose.Words é gratuita?

 R: A biblioteca Aspose.Words é uma biblioteca comercial e requer uma licença válida para uso em seus projetos. Você pode checar[Referências de API Aspose.Words para .NET](https://reference.aspose.com/words/net/) para saber mais sobre opções de licenciamento e preços.

#### P: Existem outras bibliotecas disponíveis para processamento de texto com documentos Word em .NET?

R: Sim, existem outras bibliotecas disponíveis para processamento de palavras com documentos Word em .NET, como Open XML SDK e GemBox.Document. Você pode explorar essas bibliotecas como alternativas ao Aspose.Words com base em suas necessidades e preferências específicas.