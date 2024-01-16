---
title: Configurações de largura preferidas
linktitle: Configurações de largura preferidas
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como definir larguras preferenciais de células de tabela em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/preferred-width-settings/
---

Neste tutorial, aprenderemos como definir configurações de largura preferidas para células de tabela em um documento do Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você poderá especificar diferentes larguras preferidas para as células da tabela em seus documentos do Word.

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

## Passo 3: Construindo a mesa com larguras preferidas
A seguir, construiremos uma tabela com três células que possuem diferentes larguras preferidas. Use o seguinte código:

```csharp
// Começo da mesa
builder. StartTable();

// Insira uma célula de tamanho absoluto
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Insira uma célula de tamanho relativo (em porcentagem)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Insira uma célula de tamanho automático
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Fim da mesa
builder. EndTable();
```

Aqui usamos o construtor de documentos para construir uma tabela com três células. A primeira célula tem uma largura preferencial de 40 pontos, a segunda célula tem uma largura preferencial de 20% da largura da tabela e a terceira célula tem uma largura preferencial automática que se ajusta

  dependendo do espaço disponível.

## Passo 4: Salvando o documento modificado
Finalmente, precisamos salvar o documento modificado com as configurações de largura preferidas definidas para as células da tabela. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para configurações de largura preferencial usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insira uma linha da tabela composta por três células com larguras preferidas diferentes.
	builder.StartTable();
	// Insira uma célula de tamanho absoluto.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Insira uma célula de tamanho relativo (porcentagem).
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Insira uma célula de tamanho automático.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Conclusão
Neste tutorial, aprendemos como definir configurações de largura preferidas para células de tabela em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode personalizar as larguras das células da tabela de acordo com suas necessidades específicas em seus documentos do Word.