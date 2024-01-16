---
title: Marcar colunas da tabela em um documento do Word
linktitle: Marcar colunas da tabela em um documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como marcar uma coluna de tabela em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/bookmark-table-columns/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Bookmark Table Columns na biblioteca Aspose.Words for .NET. Este recurso permite marcar uma coluna específica de uma tabela em um documento do Word e acessar o conteúdo dessa coluna.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Etapa 1: Criando a tabela

 Antes de criar um marcador em uma coluna da tabela, devemos primeiro criar a tabela usando um`DocumentBuilder`objeto. No nosso exemplo, criamos uma tabela com duas linhas e duas colunas:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## Etapa 2: Criando o marcador da coluna

 Nós usamos o`StartBookmark` método para criar um marcador em uma coluna específica da tabela. No nosso exemplo, usamos o nome "MyBookmark" para o marcador:

```csharp
builder. StartBookmark("MyBookmark");
```

## Etapa 3: acesse o conteúdo da coluna

 Percorremos todos os marcadores do documento e exibimos seus nomes. Se um marcador for uma coluna, acessamos o conteúdo dessa coluna usando o índice da coluna e o`GetText` método:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Exemplo de código-fonte para colunas da tabela de favoritos usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar a criação de um marcador em uma coluna da tabela usando Aspose.Words for .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar a função Bookmark Table Columns do Aspose.Words for .NET. Seguimos um guia passo a passo para marcar uma coluna específica de uma tabela em um documento do Word e pular para o conteúdo dessa coluna.

### Perguntas frequentes sobre colunas de tabela de marcadores em documentos do Word

#### P: Quais são os pré-requisitos para usar o recurso "Marcadores para colunas da tabela" no Aspose.Words for .NET?

R: Para usar o recurso "Marcadores para colunas de tabela" no Aspose.Words for .NET, você precisa ter conhecimento básico da linguagem C#. Você também precisa de um ambiente de desenvolvimento .NET com a biblioteca Aspose.Words instalada.

#### P: Como criar uma tabela com colunas em um documento do Word usando Aspose.Words for .NET?

 R: Para criar uma tabela com colunas em um documento do Word usando Aspose.Words for .NET, você pode usar um`DocumentBuilder` objeto para inserir células e conteúdo na tabela. Aqui está um exemplo de código:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### P: Como marcar uma coluna de tabela usando Aspose.Words for .NET?

 R: Para criar um marcador em uma coluna da tabela usando Aspose.Words for .NET, você pode usar o`StartBookmark` método do`DocumentBuilder` objeto para iniciar o marcador em uma coluna específica da tabela. Aqui está um exemplo de código:

```csharp
builder.StartBookmark("MyBookmark");
```

#### P: Como acessar o conteúdo da coluna da tabela a partir do marcador usando Aspose.Words for .NET?

R: Para acessar o conteúdo de uma coluna de tabela a partir de um marcador usando Aspose.Words for .NET, você pode percorrer todos os marcadores do documento, verificar se um marcador é uma coluna e usar o índice da coluna para acessar o conteúdo de aquela coluna. Aqui está um exemplo de código:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Faça algo com o conteúdo da coluna...
         }
     }
}
```

#### P: Existe um limite para o número de colunas que posso criar em uma tabela com marcadores de coluna?

R: Não há limite específico para o número de colunas que você pode criar em uma tabela com marcadores de coluna usando Aspose.Words for .NET. O limite depende principalmente dos recursos disponíveis no seu sistema e das especificações do formato de arquivo Word que você está usando. Porém, é recomendado não criar um número excessivamente grande de colunas, pois isso pode afetar o desempenho e a legibilidade do documento final.