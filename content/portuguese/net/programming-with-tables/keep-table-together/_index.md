---
title: Mantenha a mesa unida
linktitle: Mantenha a mesa unida
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como manter uma tabela unida em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/keep-table-together/
---

Neste tutorial, aprenderemos como manter uma tabela unida em um documento do Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você será capaz de manter uma tabela intacta sem que ela seja dividida em várias páginas de seus documentos do Word.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento e recuperando a tabela
Para iniciar o Processamento de Palavras com a tabela, precisamos carregar o documento e buscar a tabela que queremos manter unida. Siga esses passos:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Recuperar a tabela
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 3: Habilite a opção "KeepWithNext"
Para manter a tabela unida e evitar que ela se divida em várias páginas, precisamos habilitar a opção “KeepWithNext” para cada parágrafo da tabela, exceto para os últimos parágrafos da última linha da tabela. Use o seguinte código:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Aqui percorremos cada célula da tabela e habilitamos a opção "KeepWithNext" para cada parágrafo da célula, exceto para os últimos parágrafos da última linha da tabela.

## Passo 4: Salvando o documento modificado
Finalmente, precisamos salvar o documento modificado com a tabela unida. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para Keep Table Together usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Precisamos habilitar KeepWithNext para cada parágrafo da tabela para evitar que ele se quebre na página,
	// exceto os últimos parágrafos da última linha da tabela.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Conclusão
Neste tutorial, aprendemos como manter uma tabela unida em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode manter uma tabela intacta e evitar que ela se divida em várias páginas de seus documentos. Esse recurso oferece mais controle sobre a aparência e o layout das tabelas nos documentos.