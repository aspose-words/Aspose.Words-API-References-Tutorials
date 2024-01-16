---
title: Ajuste automático à largura da página
linktitle: Ajuste automático à largura da página
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como ajustar automaticamente uma tabela à largura da página em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/auto-fit-to-page-width/
---

Neste tutorial, aprenderemos como usar Aspose.Words for .NET para ajustar automaticamente uma tabela à largura da página em um documento do Word. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você será capaz de manipular tabelas em documentos do Word de forma programática.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Etapa 2: Criando e configurando o documento
Para iniciar o Processamento de Palavras com a tabela, precisamos criar um documento e configurar o gerador de documentos. Siga esses passos:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e o gerador de documentos
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Passo 3: Inserindo e Configurando a Tabela
A seguir, inseriremos uma tabela no documento com largura que ocupa metade da largura da página. Use o seguinte código:

```csharp
// Insira a tabela e configure sua largura
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Aqui usamos o construtor de documentos para começar a criar a tabela, inserir células e definir a largura preferida da tabela para 50% da largura da página. Em seguida, adicionamos texto em cada célula.

## Passo 4: Salvando o documento modificado
Por fim, precisamos salvar o documento modificado com a tabela ajustada à largura da página. Use o seguinte código:

```csharp
// Salve o documento modificado
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.
  
### Exemplo de código-fonte para ajuste automático à largura da página usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insira uma tabela com largura que ocupe metade da largura da página.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Conclusão
Neste tutorial, aprendemos como ajustar automaticamente uma tabela à largura da página em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode manipular tabelas em seus documentos do Word de forma programática. Esta funcionalidade permite adaptar de forma dinâmica a largura da tabela de acordo com a página, oferecendo assim um documento profissional e visualmente apelativo.