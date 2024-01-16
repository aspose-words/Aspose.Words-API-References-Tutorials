---
title: Expanda a formatação nas células e na linha do estilo
linktitle: Expanda a formatação nas células e na linha do estilo
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para expandir a formatação para células e linhas de um estilo de tabela usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

Neste tutorial, orientaremos você no processo passo a passo para expandir a formatação para células e linhas de um estilo usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. No final deste tutorial, você saberá como aplicar formatação de estilo de tabela a células e linhas específicas em seus documentos do Word usando Aspose.Words for .NET.


## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. É aqui que o seu documento do Word está localizado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: carregar o documento existente
 Em seguida, você precisa carregar o documento Word existente em uma instância do`Document` aula.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Etapa 3: vá para a primeira célula da primeira tabela
 Para começar, precisamos navegar até a primeira célula da primeira tabela do documento. Nós usamos o`GetChild()` e`FirstRow.FirstCell` métodos para obter a referência à primeira célula.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Etapa 4: mostrar a formatação inicial da célula
Antes de expandir os estilos da tabela, exibimos a cor de fundo atual da célula. Deve estar vazio porque a formatação atual é armazenada no estilo da tabela.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Etapa 5: Expanda os estilos de tabela para formatação direta
 Agora expandimos os estilos de tabela para formatação direta usando o documento`ExpandTableStylesToDirectFormatting()` método.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Etapa 6: mostrar a formatação das células após a expansão do estilo
Agora exibimos a cor de fundo da célula após expandir os estilos da tabela. Uma cor de fundo azul deve ser aplicada no estilo da tabela.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Exemplo de código-fonte para expandir a formatação em células e linha do estilo usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Obtenha a primeira célula da primeira tabela do documento.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Primeiro imprima a cor do sombreamento da célula.
	// Deve estar vazio, pois o sombreamento atual é armazenado no estilo de tabela.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Agora imprima o sombreamento das células após expandir os estilos de tabela.
	// Uma cor de padrão de fundo azul deveria ter sido aplicada a partir do estilo de tabela.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Conclusão
Neste tutorial, aprendemos como expandir a formatação para células e linhas de um estilo de tabela usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode aplicar facilmente a formatação de estilo de tabela a células e linhas específicas em seus documentos do Word. Aspose.Words oferece uma API poderosa e flexível para manipular e formatar tabelas em seus documentos. Com esse conhecimento, você pode personalizar ainda mais o layout e a apresentação dos seus documentos Word.