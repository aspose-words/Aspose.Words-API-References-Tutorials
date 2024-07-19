---
title: Modificar formatação de linha
linktitle: Modificar formatação de linha
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para alterar a formatação das linhas da tabela usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

Neste tutorial, orientaremos você no processo passo a passo para alterar a formatação de uma linha da tabela usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como alterar bordas, altura e quebra de linha de uma linha de tabela em seus documentos Word usando Aspose.Words for .NET.

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

## Passo 3: Acesse a linha para modificar
 Para alterar a formatação de uma linha da tabela, precisamos navegar até a linha específica da tabela. Nós usamos o`GetChild()`e`FirstRow` métodos para obter a referência à primeira linha da tabela.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## Etapa 4: alterar a formatação da linha
 Agora podemos alterar a formatação da linha usando as propriedades do`RowFormat` aula. Por exemplo, podemos remover bordas de linha, definir altura automática e permitir quebra de linha.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Exemplo de código-fonte para modificar formatação de linha usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Recupera a primeira linha da tabela.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## Conclusão
Neste tutorial, aprendemos como alterar a formatação de uma linha da tabela usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode ajustar facilmente as bordas, a altura e a quebra de linha das tabelas em seus documentos do Word. Aspose.Words oferece uma API poderosa e flexível para manipular e formatar tabelas em seus documentos. Com esse conhecimento, você pode personalizar o layout visual de suas tabelas de acordo com suas necessidades específicas.