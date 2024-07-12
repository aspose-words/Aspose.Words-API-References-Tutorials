---
title: Combinar linhas
linktitle: Combinar linhas
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como combinar linhas de tabela em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/combine-rows/
---

Neste tutorial, aprenderemos como usar Aspose.Words for .NET para combinar linhas de tabelas em um documento do Word. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. No final deste tutorial, você será capaz de manipular e mesclar linhas de tabelas em seus documentos do Word de forma programática.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento e acessando as tabelas
Para iniciar o Processamento de Palavras com tabelas, precisamos carregar o documento que as contém e acessá-las. Siga esses passos:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Tables.docx");

// Acesso às tabelas
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 3: combinar linhas da tabela
seguir, combinaremos as linhas da segunda tabela com o final da primeira tabela. Use o seguinte código:

```csharp
// Combinação de linhas da tabela
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Aqui usamos um`while` loop para iterar sobre todas as linhas do segundo array e adicioná-las ao final do primeiro array usando o`Add` método. A seguir, removemos a segunda tabela do documento usando o`Remove` método.

## Passo 4: Salvando o documento modificado
Finalmente, precisamos salvar o documento modificado com as linhas combinadas da tabela. Use o seguinte código:

```csharp
// Salve o documento modificado
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para Combine Rows usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// As linhas da segunda tabela serão anexadas ao final da primeira tabela.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Anexar todas as linhas da tabela atual às próximas tabelas
	// com diferentes contagens e larguras de células podem ser unidas em uma tabela.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Conclusão
Neste tutorial, aprendemos como combinar linhas de tabelas em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode manipular linhas de tabela em seus documentos do Word de forma programática. Este recurso permite mesclar e organizar seus dados com eficiência em uma tabela.