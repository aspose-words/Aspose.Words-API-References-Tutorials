---
title: Definir formatação de linha da tabela
linktitle: Definir formatação de linha da tabela
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para definir a formatação de linhas da tabela usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

Neste tutorial, orientaremos você no processo passo a passo para definir a formatação das linhas da tabela usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como ajustar a altura e o preenchimento de uma linha da tabela em seus documentos do Word usando Aspose.Words for .NET.

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. Este é o local onde você deseja salvar o documento do Word editado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Crie um novo documento e construtor de documentos
 Em seguida, você precisa criar uma nova instância do`Document` classe e um construtor de documento para esse documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: inicie uma nova tabela e adicione uma célula
Para começar a criar a tabela, usamos o`StartTable()` método do construtor do documento, então adicionamos uma célula à tabela usando o`InsertCell()` método.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Passo 4: Defina a formatação da linha
 Agora podemos definir a formatação da linha acessando o`RowFormat` objeto do`DocumentBuilder` objeto. Podemos definir a altura da linha e as margens (preenchimentos) usando as propriedades correspondentes.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Etapa 5: definir as margens da tabela
 A seguir, podemos definir os preenchimentos da tabela acessando as propriedades correspondentes do`Table` objeto. Essas margens serão aplicadas a todas as linhas da tabela.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Etapa 6: adicione conteúdo à linha
 Finalmente, podemos adicionar conteúdo à linha usando o construtor de documentos`Writeln()` método.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Passo 7: Conclua a tabela e salve o documento
Em

 final, terminamos de criar a tabela usando o`EndRow()`e`EndTable()` método, então salvamos o documento modificado em um arquivo.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Exemplo de código-fonte para definir formatação de linha de tabela usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Essas propriedades de formatação são definidas na tabela e aplicadas a todas as linhas da tabela.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Conclusão
Neste tutorial, aprendemos como definir a formatação de linhas da tabela usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode ajustar facilmente a altura e as margens das linhas da tabela em seus documentos do Word. Aspose.Words oferece uma API poderosa e flexível para manipular e formatar tabelas em seus documentos. Com esse conhecimento, você pode personalizar o layout visual de suas tabelas de acordo com suas necessidades específicas.