---
title: Crie uma tabela simples
linktitle: Crie uma tabela simples
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar uma tabela simples em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/create-simple-table/
---

Neste tutorial, aprenderemos como criar uma tabela simples em um documento Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você poderá criar tabelas personalizadas em seus documentos do Word de forma programática.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Criando o documento e inicializando o gerador de documentos
Para começar a construir a tabela, precisamos criar um novo documento e inicializar o construtor de documentos. Siga esses passos:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Crie o documento e inicialize o gerador de documentos
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 3: Construindo a matriz
A seguir, construiremos a tabela usando os métodos fornecidos pelo construtor de documentos. Use o seguinte código:

```csharp
// Comece a construção do array
builder. StartTable();

// Construção da primeira célula da primeira linha
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Construção da segunda célula da primeira linha
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

// Chame o método a seguir para finalizar a primeira linha e iniciar uma nova linha
builder. EndRow();

// Construção da primeira célula da segunda linha
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Construção da segunda célula da segunda linha
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Chame o próximo método para finalizar a segunda linha
builder. EndRow();

// Indicação de que a construção da mesa está finalizada
builder. EndTable();
```

 Aqui usamos o construtor de documentos para construir a tabela passo a passo. Começamos ligando`StartTable()` para inicializar a tabela, então use`InsertCell()` para inserir células e`Write()` para adicionar conteúdo a cada célula. Nós também usamos`EndRow()` para encerrar uma linha e iniciar uma nova linha. Finalmente, chamamos`EndTable()` para indicar que a construção da tabela está concluída.

## Etapa 4: salve o documento
Finalmente, precisamos salvar

  documento com a tabela criada. Use o seguinte código:

```csharp
// Salve o documento
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para criar tabela simples usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Comece a construir a mesa.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Construa a segunda célula.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Chame o método a seguir para encerrar a linha e iniciar uma nova linha.
	builder.EndRow();
	// Construa a primeira célula da segunda linha.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Construa a segunda célula.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	// Sinalize que terminamos de construir a mesa.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Conclusão
Neste tutorial, aprendemos como criar uma tabela simples em um documento Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode criar tabelas personalizadas em seus documentos do Word de forma programática. Este recurso permite formatar e organizar seus dados de forma estruturada e clara.