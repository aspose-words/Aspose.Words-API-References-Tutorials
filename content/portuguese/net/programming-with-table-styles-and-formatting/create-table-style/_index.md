---
title: Criar estilo de tabela
linktitle: Criar estilo de tabela
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para criar um estilo de tabela personalizado usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/create-table-style/
---

Neste tutorial, orientaremos você no processo passo a passo para criar um estilo de tabela usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como criar um estilo personalizado para suas tabelas em documentos Word usando Aspose.Words for .NET.

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

## Etapa 3: inicie uma nova tabela e adicione células
Para começar a criar a tabela, usamos o`StartTable()` método do construtor de documentos, então adicionamos células à tabela usando o`InsertCell()` método e escrevemos o conteúdo das células usando o`Write()` método.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Etapa 4: crie um estilo de tabela
 Agora podemos criar um estilo de tabela usando o`TableStyle` classe e o`Add()` método do documento`s `Coleção de estilos. Definimos as propriedades do estilo, como bordas, margens e preenchimentos.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Etapa 5: aplique o estilo de tabela à tabela
 Finalmente, aplicamos o estilo de tabela que criamos à tabela usando o`Style` propriedade da tabela.

```csharp
table.Style = tableStyle;
```

## Etapa 6: salve o documento modificado
Por fim, salve o documento modificado em um arquivo. Você pode escolher um nome e local apropriado para o documento de saída.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Parabéns! Agora você criou um estilo personalizado para sua tabela usando Aspose.Words for .NET.

### Exemplo de código-fonte para criar estilo de tabela usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Conclusão
Neste tutorial, aprendemos como criar um estilo de tabela usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode personalizar facilmente o estilo de suas tabelas em documentos do Word. Aspose.Words oferece uma API poderosa e flexível para manipular e formatar tabelas em seus documentos. Com esse conhecimento, você poderá melhorar a apresentação visual de seus documentos Word e atender necessidades específicas.