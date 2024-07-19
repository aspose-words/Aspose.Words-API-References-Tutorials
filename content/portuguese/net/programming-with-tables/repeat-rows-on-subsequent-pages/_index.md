---
title: Repetir linhas nas páginas subsequentes
linktitle: Repetir linhas nas páginas subsequentes
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como repetir linhas da tabela nas páginas subsequentes em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

Neste tutorial, aprenderemos como repetir as linhas de uma tabela nas páginas subsequentes de um documento Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você poderá especificar linhas para repetir nas páginas subsequentes de sua tabela em seus documentos do Word.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Criando o documento e inicializando o gerador de documentos
Para iniciar o processamento de palavras com o documento e o gerador de documentos, siga estas etapas:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Criação de documento
Document doc = new Document();

// Inicialize o gerador de documentos
DocumentBuilder builder = new DocumentBuilder(doc);
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Passo 3: Construindo a tabela com linhas repetidas
A seguir, construiremos uma tabela com linhas repetidas nas páginas subsequentes. Use o seguinte código:

```csharp
// Começo da mesa
builder. StartTable();

// Configuração dos parâmetros da primeira linha (linhas de cabeçalho)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Insira a primeira célula da primeira linha
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Insira a segunda célula da primeira linha
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Configure os parâmetros das seguintes linhas
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Loop para inserir as células nas linhas seguintes
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Fim da mesa
builder. EndTable();
```

 Aqui usamos o construtor de documentos para construir uma tabela com duas linhas de cabeçalho e várias linhas de dados. O`RowFormat.HeadingFormat` parâmetros são usados para marcar linhas de cabeçalho que devem ser repetidas nas páginas subsequentes.

## Passo 4: Salvando o documento modificado
Finalmente EUA

  precisa salvar o documento modificado com as linhas de cabeçalho repetidas nas páginas subsequentes da tabela. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para repetir linhas em páginas subsequentes usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Conclusão
Neste tutorial, aprendemos como repetir as linhas de uma tabela nas páginas subsequentes de um documento Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode especificar quais linhas repetir de acordo com suas necessidades específicas em seus documentos do Word.