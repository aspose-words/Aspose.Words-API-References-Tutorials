---
title: Ajustar automaticamente a tabela ao conteúdo
linktitle: Ajustar automaticamente a tabela ao conteúdo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como ajustar automaticamente uma tabela ao seu conteúdo em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/auto-fit-table-to-contents/
---

Neste tutorial, aprenderemos como usar Aspose.Words for .NET para ajustar automaticamente uma tabela ao seu conteúdo em um documento do Word usando C#. Seguiremos o processo passo a passo de escrita de código para obter essa funcionalidade. Ao final deste tutorial, você terá uma compreensão clara de como manipular tabelas em documentos do Word de forma programática.

## Etapa 1: configurar o projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Etapa 2: carregue o documento do Word
Para iniciar o Processamento de Palavras com a tabela, precisamos carregar o documento Word que contém a tabela. Siga esses passos:

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Carregue o documento do Word
Document doc = new Document(dataDir + "Tables.docx");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real do seu documento.

## Etapa 3: acesse a tabela e ajuste-a automaticamente ao conteúdo
Em seguida, precisamos acessar a tabela dentro do documento e aplicar o comportamento de ajuste automático. Use o seguinte código:

```csharp
// Acesse a tabela
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// Ajustar automaticamente a tabela ao seu conteúdo
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 Aqui, estamos lançando o primeiro nó filho do tipo`Table` do documento e, em seguida, usando o`AutoFit` método com o`AutoFitToContents` comportamento para ajustar a largura da tabela para ajustar seu conteúdo.

## Etapa 4: salve o documento modificado
Finalmente, precisamos salvar o documento modificado com a tabela ajustada automaticamente. Use o seguinte código:

```csharp
// Salve o documento modificado
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para ajuste automático da tabela ao conteúdo usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## Conclusão
Neste tutorial, aprendemos como ajustar automaticamente uma tabela ao seu conteúdo em um documento do Word usando Aspose.Words for .NET. Seguindo o guia passo a passo e implementando o código C# fornecido, você pode manipular tabelas em seus documentos do Word de forma programática. Isso permite ajustar dinamicamente a largura da tabela com base em seu conteúdo, proporcionando um documento mais profissional e visualmente atraente.