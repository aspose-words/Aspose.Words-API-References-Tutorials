---
title: Aplicar formatação de linha
linktitle: Aplicar formatação de linha
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para aplicar formatação de linha a uma tabela usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

Neste tutorial, orientaremos você no processo passo a passo para aplicar a formatação de linha a uma tabela usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você terá uma compreensão clara de como formatar linhas de tabela em seus documentos do Word usando Aspose.Words for .NET.

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

## Etapa 3: iniciar um novo quadro
 Para aplicar a formatação de linha, devemos primeiro iniciar uma nova tabela usando o`StartTable()` método do construtor do documento.

```csharp
Table table = builder. StartTable();
```

## Etapa 4: insira a célula e vá para o formato de linha
Agora podemos inserir uma célula na tabela e acessar o formato de linha dessa célula usando o construtor de documentos`InsertCell()`e`RowFormat` métodos.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Etapa 5: definir a altura da linha
 Para definir a altura da linha, usamos o`Height`e`HeightRule` propriedades do formato de linha. Neste exemplo, definimos uma altura de linha de 100 pontos e usamos o`Exactly` regra.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Passo 6: Definir a formatação da tabela
 Algumas propriedades de formatação podem ser definidas na própria tabela e aplicadas a todas as linhas da tabela. Neste exemplo, definimos as propriedades da margem da tabela usando o método`LeftPadding`, `RightPadding`, `TopPadding`e`BottomPadding` propriedades.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Etapa 7: adicione conteúdo à linha
Agora podemos

 Adicionaremos conteúdo à linha usando os métodos do construtor do documento. Neste exemplo, usamos o`Writeln()` método para adicionar texto à linha.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Passo 8: Finalize a linha e a mesa
 Depois de adicionar o conteúdo à linha, podemos finalizá-la usando o`EndRow()` método e então finalize a tabela usando o`EndTable()` método.

```csharp
builder. EndRow();
builder. EndTable();
```

## Etapa 9: salve o documento modificado
Finalmente, salvamos o documento modificado em um arquivo. Você pode escolher um nome e local apropriado para o documento de saída.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Parabéns! Agora você aplicou a formatação de linha a uma tabela usando Aspose.Words for .NET.

### Exemplo de código-fonte para Aplicar formatação de linha usando Aspose.Words for .NET 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Conclusão
Neste tutorial, aprendemos como aplicar formatação de linha a uma tabela usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode integrar facilmente essa funcionalidade em seus projetos C#. Manipular a formatação de linhas da tabela é um aspecto essencial do processamento de documentos, e Aspose.Words oferece uma API poderosa e flexível para conseguir isso. Com esse conhecimento, você poderá melhorar a apresentação visual de seus documentos Word e atender a requisitos específicos.