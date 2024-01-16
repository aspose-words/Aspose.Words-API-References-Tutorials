---
title: Tabela dividida
linktitle: Tabela dividida
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como dividir uma tabela em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/split-table/
---

Neste tutorial, aprenderemos como dividir uma tabela em um documento Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você poderá dividir uma tabela de uma determinada linha em seus documentos do Word.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento
Para iniciar o processamento de palavras com o documento, siga estas etapas:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Tables.docx");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos e forneça o nome de arquivo correto.

## Passo 3: Dividindo a mesa
A seguir dividiremos a tabela de uma determinada linha. Use o seguinte código:

```csharp
// Recuperar a primeira tabela
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Determinação da linha a partir da qual dividir a tabela
Row row = firstTable.Rows[2];

// Crie um novo contêiner para a tabela dividida
Table table = (Table)firstTable.Clone(false);

// Insira o contêiner após a tabela original
firstTable.ParentNode.InsertAfter(table, firstTable);

// Adicione um parágrafo intermediário para manter a distância entre as tabelas
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Mover linhas da tabela original para a tabela dividida
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Aqui usamos o documento para recuperar a primeira tabela do nó do documento. Em seguida determinamos a linha da qual queremos dividir a tabela, neste exemplo é a terceira linha (índice 2). Em seguida, criamos um novo contêiner clonando a tabela original e inserindo-o após a tabela original. Também adicionamos um parágrafo tampão para manter a distância entre as duas tabelas. Em seguida, movemos as linhas da tabela original para a tabela dividida usando um loop do-while até chegarmos à linha especificada.

## Passo 4: Salvando o documento modificado
Finalmente, precisamos salvar o

  documento modificado com a tabela dividida. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para Split Table usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Dividiremos a tabela na terceira linha (inclusive).
Row row = firstTable.Rows[2];
// Crie um novo contêiner para a tabela dividida.
Table table = (Table) firstTable.Clone(false);
// Insira o recipiente após o original.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Adicione um parágrafo intermediário para garantir que as tabelas permaneçam separadas.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Conclusão
Neste tutorial, aprendemos como dividir uma tabela em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode facilmente dividir tabelas de uma determinada linha em seus documentos do Word.