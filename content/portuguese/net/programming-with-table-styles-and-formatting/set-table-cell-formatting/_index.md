---
title: Definir formatação de células de tabela
linktitle: Definir formatação de células de tabela
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para definir a formatação de células de tabela usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/set-table-cell-formatting/
---

Neste tutorial, orientaremos você no processo passo a passo para definir a formatação de uma célula de tabela usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como ajustar a largura e as margens (preenchimentos) de uma célula nas tabelas de seus documentos Word usando Aspose.Words for .NET.

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
builder. StartTable();
builder. InsertCell();
```

## Etapa 4: definir a formatação das células
 Agora podemos definir a formatação da célula acessando o`CellFormat` objeto do`DocumentBuilder` objeto. Podemos definir a largura da célula e as margens (preenchimentos) usando as propriedades correspondentes.

```csharp
CellFormat cellFormat = builder. CellFormat;
cellFormat. Width = 250;
cellFormat. LeftPadding = 30;
cellFormat. RightPadding = 30;
cellFormat. TopPadding = 30;
cellFormat.BottomPadding = 30;
```

## Etapa 5: adicione conteúdo à célula
 Então podemos adicionar conteúdo à célula usando o construtor de documentos`Writeln()` método.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Passo 6: Conclua a tabela e salve o documento
 Por fim, finalizamos a criação da tabela usando o`EndRow()` método e`EndTable()`, então salvamos o documento modificado em um arquivo.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

### Exemplo de código-fonte para definir formatação de células de tabela usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	CellFormat cellFormat = builder.CellFormat;
	cellFormat.Width = 250;
	cellFormat.LeftPadding = 30;
	cellFormat.RightPadding = 30;
	cellFormat.TopPadding = 30;
	cellFormat.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
```

## Conclusão
Neste tutorial, aprendemos como definir a formatação de uma célula de tabela usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode ajustar facilmente a largura e as margens de uma célula em suas tabelas em seus documentos do Word. Aspose.Words oferece uma API poderosa e flexível para manipular e formatar tabelas em seus documentos. Com esse conhecimento, você pode personalizar o layout visual de suas tabelas de acordo com suas necessidades específicas.