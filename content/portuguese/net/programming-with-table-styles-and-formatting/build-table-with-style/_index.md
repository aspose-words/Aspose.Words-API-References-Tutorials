---
title: Construa uma mesa com estilo
linktitle: Construa uma mesa com estilo
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para construir uma tabela com estilo personalizado usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

Neste tutorial, orientaremos você no processo passo a passo para construir uma tabela estilizada usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como criar uma tabela com estilo customizado em seus documentos Word usando Aspose.Words for .NET.

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

## Etapa 3: inicie uma nova tabela e insira uma célula
 Para começar a construir a tabela, usamos o`StartTable()` método do construtor de documentos, então inserimos uma célula na tabela usando o`InsertCell()` método.

```csharp
Table table = builder. StartTable();
builder.InsertCell();
```

## Passo 4: Defina o estilo da tabela
 Agora podemos definir o estilo da tabela usando o`StyleIdentifier` propriedade. Neste exemplo, estamos usando o estilo “MediumShading1Accent1”.

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Etapa 5: aplicar opções de estilo à tabela
 Podemos especificar quais características devem ser formatadas pelo estilo usando o comando`StyleOptions`propriedade da matriz. Neste exemplo, aplicamos as seguintes opções: “FirstColumn”, “RowBands” e “FirstRow”.

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Etapa 6: ajustar automaticamente o tamanho da tabela
 Para ajustar automaticamente o tamanho do array com base em seu conteúdo, usamos o comando`AutoFit()` método com o`AutoFitBehavior.AutoFitToContents` comportamento.

```csharp
table.AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Etapa 7: adicionar conteúdo às células
 Agora podemos adicionar conteúdo às células usando o`Writeln()`e`InsertCell()` métodos do construtor de documentos. Neste exemplo, adicionamos os cabeçalhos para "Item" e "Quantidade (

kg)" e os dados correspondentes.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writen("Quantity (kg)");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writen("40");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();
```

## Etapa 8: salve o documento modificado
Finalmente, salvamos o documento modificado em um arquivo. Você pode escolher um nome e local apropriado para o documento de saída.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Parabéns! Agora você construiu uma tabela com estilo personalizado usando Aspose.Words for .NET.

### Exemplo de código-fonte para Build Table With Style usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
// Devemos inserir pelo menos uma linha antes de definir qualquer formatação de tabela.
builder.InsertCell();
// Defina o estilo de tabela usado com base no identificador de estilo exclusivo.
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
// Aplique quais recursos devem ser formatados pelo estilo.
table.StyleOptions =
	TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
table.AutoFit(AutoFitBehavior.AutoFitToContents);
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder.InsertCell();
builder.Writeln("Quantity (kg)");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Apples");
builder.InsertCell();
builder.Writeln("20");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Bananas");
builder.InsertCell();
builder.Writeln("40");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Carrots");
builder.InsertCell();
builder.Writeln("50");
builder.EndRow();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Conclusão
Neste tutorial, aprendemos como construir uma tabela estilizada usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode personalizar facilmente o estilo de suas tabelas em documentos do Word. Aspose.Words oferece uma API poderosa e flexível para manipular e formatar tabelas em seus documentos. Com esse conhecimento, você poderá melhorar a apresentação visual de seus documentos Word e atender necessidades específicas.