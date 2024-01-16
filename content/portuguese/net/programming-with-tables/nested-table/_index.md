---
title: Tabela aninhada
linktitle: Tabela aninhada
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar uma tabela aninhada em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/nested-table/
---

Neste tutorial, aprenderemos como criar uma tabela aninhada em um documento do Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você será capaz de criar tabelas aninhadas em seus documentos do Word de forma programática.

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

## Etapa 3: construindo a tabela aninhada
A seguir, construiremos a tabela aninhada inserindo células na tabela externa e criando uma nova tabela dentro da primeira célula. Use o seguinte código:

```csharp
// Insira a primeira célula da tabela externa
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Insira a segunda célula da tabela externa
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Rescisão da tabela externa
builder. EndTable();

// Vá para a primeira célula da tabela externa
builder.MoveTo(cell.FirstParagraph);

// Construa a mesa interna
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Fim da mesa interna
builder. EndTable();
```

Aqui usamos o construtor de documentos para inserir células e conteúdo na tabela externa. Em seguida, movemos o cursor do construtor de documentos para a primeira célula da tabela externa e construímos uma nova tabela interna, inserindo células e conteúdo.

## Passo 4: Salvando o documento modificado
Finalmente, precisamos salvar o documento modificado com a tabela aninhada. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Certifique-se de especificar o caminho e o nome do arquivo corretos para o documento de saída.

### Exemplo de código-fonte para tabela aninhada usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Esta chamada é importante para criar uma tabela aninhada na primeira tabela.
	// Sem esta chamada, as células inseridas abaixo serão anexadas à tabela externa.
	builder.EndTable();
	// Vá para a primeira célula da tabela externa.
	builder.MoveTo(cell.FirstParagraph);
	// Construa a mesa interna.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Conclusão
Neste tutorial, aprendemos como criar uma tabela aninhada em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode criar tabelas aninhadas de acordo com suas necessidades específicas em seus documentos do Word de forma programática.
