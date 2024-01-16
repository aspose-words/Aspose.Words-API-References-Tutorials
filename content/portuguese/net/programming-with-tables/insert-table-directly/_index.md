---
title: Inserir tabela diretamente
linktitle: Inserir tabela diretamente
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir uma tabela diretamente em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/insert-table-directly/
---

Neste tutorial, aprenderemos como inserir diretamente uma tabela em um documento do Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você será capaz de inserir tabelas diretamente em seus documentos do Word de forma programática.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Etapa 2: Criando o Documento e a Tabela
Para iniciar o processamento de palavras com o array, precisamos criar um novo documento e inicializar o array. Siga esses passos:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Criação de documento
Document doc = new Document();

//Crie a matriz
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 3: Construindo a matriz
A seguir, construiremos a tabela adicionando linhas e células. Use o seguinte código como exemplo:

```csharp
// Crie a primeira linha
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Crie a primeira célula
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Duplique a célula para a segunda célula da linha
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Aqui criamos uma linha com o`AllowBreakAcrossPages` propriedade definida como`true` para permitir quebra de página entre linhas. Em seguida, criamos uma célula com fundo colorido, largura fixa e conteúdo de texto especificado. Em seguida, duplicamos esta célula para criar a segunda célula na linha.

## Etapa 4: tabela de ajuste automático
Podemos aplicar ajustes automáticos à tabela para formatá-la corretamente. Use o seguinte código:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Esta linha de código aplica um ajuste automático com base em larguras fixas de colunas.

## Passo 5: Registrando o

  documento modificado
Finalmente, precisamos salvar o documento modificado com a tabela inserida diretamente. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para inserir tabela diretamente usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Começamos criando o objeto tabela. Observe que devemos passar o objeto document
	//ao construtor de cada nó. Isso ocorre porque cada nó que criamos deve pertencer
	// para algum documento.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Aqui poderíamos chamar GaranteMinimum para criar as linhas e células para nós. Este método é usado
	// para garantir que o nó especificado seja válido. Neste caso, uma tabela válida deve ter pelo menos uma linha e uma célula.
	// Em vez disso, nós mesmos cuidaremos da criação da linha e da tabela.
	// Esta seria a melhor maneira de fazer isso se estivéssemos criando uma tabela dentro de um algoritmo.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Agora podemos aplicar quaisquer configurações de ajuste automático.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Repetiríamos então o processo para as outras células e linhas da tabela.
	// Também podemos acelerar as coisas clonando células e linhas existentes.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Conclusão
Neste tutorial, aprendemos como inserir diretamente uma tabela em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode inserir tabelas diretamente em seus documentos do Word de forma programática. Este recurso permite criar e personalizar tabelas de acordo com suas necessidades específicas.