---
title: Mesclagem vertical
linktitle: Mesclagem vertical
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como mesclar células verticais em uma tabela em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/vertical-merge/
---

Neste tutorial, aprenderemos como mesclar células verticais em uma tabela em um documento do Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você poderá mesclar células verticais em suas tabelas em documentos do Word.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento
Para iniciar o processamento de palavras com o documento, siga estas etapas:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie um novo documento
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 3: mesclando células verticais
A seguir iremos mesclar as células verticais da tabela. Use o seguinte código:

```csharp
// Inserir uma célula
builder. InsertCell();

// Aplique a mesclagem vertical à primeira célula
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Insira outra célula
builder. InsertCell();

// Não aplique nenhuma mesclagem vertical à célula
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Inserir uma célula
builder. InsertCell();

// Aplique a mesclagem vertical com a célula anterior
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Insira outra célula
builder. InsertCell();

// Não aplique nenhuma mesclagem vertical à célula
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Finalizar a criação da tabela
builder. EndTable();
```

Neste código, usamos o construtor DocumentBuilder para inserir células em uma tabela. Aplicamos a mesclagem vertical às células usando a propriedade CellFormat.VerticalMerge. Usamos CellMerge.First para a primeira mesclagem de células, CellMerge.Previous para mesclar com a célula anterior e CellMerge.None para nenhuma mesclagem vertical.

## Passo 4: Salvando o documento modificado
Finalmente, precisamos salvar o documento modificado com as células mescladas. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para Vertical Merge usando Aspose.Words for .NET 
```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Esta célula é mesclada verticalmente com a célula acima e deve estar vazia.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Conclusão
Neste tutorial, aprendemos como mesclar células verticais em uma tabela em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode facilmente mesclar células verticais em suas tabelas.