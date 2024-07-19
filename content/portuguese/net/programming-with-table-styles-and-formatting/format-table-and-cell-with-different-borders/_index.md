---
title: Formatar tabela e célula com bordas diferentes
linktitle: Formatar tabela e célula com bordas diferentes
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para formatar tabela e célula com bordas diferentes usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

Neste tutorial, orientaremos você no processo passo a passo para formatar uma tabela e uma célula com bordas diferentes usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. No final deste tutorial, você saberá como aplicar bordas personalizadas a tabelas e células específicas em seus documentos do Word usando Aspose.Words for .NET.

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
Para começar a criar a tabela, usamos o`StartTable()` método do construtor de documentos, então adicionamos células à tabela usando o`InsertCell()` método e escrevemos o conteúdo das células usando o`Writeln()` método.

```csharp
Table table = builder. StartTable();
builder.InsertCell();
// Defina bordas para toda a mesa.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Defina o preenchimento para esta célula.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Especifique um preenchimento de célula diferente para a segunda célula.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Limpe a formatação de células de operações anteriores.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Crie bordas mais grossas para a primeira célula desta linha. Será diferente
// em relação às bordas definidas para a tabela.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Etapa 4: salve o documento

  alteradas
Por fim, salve o documento modificado em um arquivo. Você pode escolher um nome e local apropriado para o documento de saída.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Parabéns! Agora você formatou uma tabela e uma célula com bordas diferentes usando Aspose.Words for .NET.

### Exemplo de código-fonte para formatar tabela e célula com bordas diferentes usando Aspose.Words para .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
builder.InsertCell();
//Defina as bordas de toda a tabela.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Defina o sombreamento celular para esta célula.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Especifique um sombreamento de célula diferente para a segunda célula.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Limpe a formatação das células das operações anteriores.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Crie bordas maiores para a primeira célula desta linha. Isso será diferente
// em comparação com as bordas definidas para a mesa.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Conclusão
Neste tutorial, aprendemos como formatar uma tabela e uma célula com bordas diferentes usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode personalizar facilmente as bordas da tabela e das células em seus documentos do Word. Aspose.Words oferece uma API poderosa e flexível para manipular e formatar tabelas em seus documentos. Com esse conhecimento, você poderá melhorar a apresentação visual de seus documentos Word e atender necessidades específicas.