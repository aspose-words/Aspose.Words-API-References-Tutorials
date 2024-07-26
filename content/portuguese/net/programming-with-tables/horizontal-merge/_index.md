---
title: Mesclagem horizontal
linktitle: Mesclagem horizontal
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como mesclar células horizontalmente em uma tabela do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/horizontal-merge/
---

Neste tutorial, aprenderemos como mesclar células horizontalmente em uma tabela em um documento do Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você será capaz de mesclar células horizontalmente em suas tabelas do Word de forma programática.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Criando o documento e inicializando o gerador de documentos
Para iniciar o Processamento de Palavras com a tabela e as células, precisamos criar um novo documento e inicializar o gerador de documentos. Siga esses passos:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Crie o documento e inicialize o gerador de documentos
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 3: Construindo a tabela com mesclagem horizontal de células
seguir, construiremos a tabela e aplicaremos a mesclagem horizontal de células usando as propriedades fornecidas pelo Aspose.Words for .NET. Use o seguinte código:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Esta célula é mesclada com a anterior e deve estar vazia.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Aqui usamos o construtor de documentos para construir a tabela e definir as propriedades de mesclagem horizontal das células. Nós usamos o`HorizontalMerge` propriedade do`CellFormat` objeto para especificar o tipo de mesclagem horizontal a ser aplicada a cada célula. Usando`CellMerge.First` mesclamos a primeira célula com a próxima, enquanto usamos`CellMerge.Previous` mesclamos a célula atual com a célula anterior.`CellMerge.None` indica que a célula não deve ser mesclada.

## Passo 4: Salvando o documento modificado
Finalmente, precisamos salvar o documento modificado com as células mescladas horizontalmente. Use o seguinte código:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para mesclagem horizontal usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Esta célula é mesclada com a anterior e deve estar vazia.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Conclusão
Neste tutorial, aprendemos como mesclar células horizontalmente em uma tabela em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode aplicar a mesclagem horizontal de células em suas tabelas do Word de forma programática. Este recurso permite criar layouts de tabelas mais complexos e organizar melhor seus dados.