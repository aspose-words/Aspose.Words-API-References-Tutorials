---
title: Clonar tabela completa
linktitle: Clonar tabela completa
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como clonar uma tabela inteira em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/clone-complete-table/
---

Neste tutorial, aprenderemos como usar Aspose.Words for .NET para clonar uma tabela inteira em um documento do Word. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. No final deste tutorial, você poderá clonar tabelas em seus documentos do Word de forma programática.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento e acessando a tabela
Para iniciar o Processamento de Palavras com a tabela, precisamos carregar o documento que a contém e acessá-lo. Siga esses passos:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Tables.docx");

// Acesso à matriz
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos.

## Etapa 3: clone completo do array
A seguir, clonaremos a tabela inteira e a inseriremos no documento após o original. Use o seguinte código:

```csharp
// Clonar a matriz
Table tableClone = (Table)table.Clone(true);

// Insira a tabela clonada no documento após o original
table.ParentNode.InsertAfter(tableClone, table);

// Insira um parágrafo vazio entre as duas tabelas
// Caso contrário, eles serão combinados em um só ao salvar (isso ocorre devido à validação do documento)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Aqui estamos usando o`Clone` método para criar uma cópia completa do array. Então usamos`InsertAfter` para inserir a tabela clonada no documento, após a tabela original. Também adicionamos um parágrafo vazio entre as duas tabelas para evitar que sejam mescladas ao salvar.

## Passo 4: Salvando o documento modificado
Finalmente, precisamos salvar o documento modificado com a tabela clonada. Use o seguinte código:

```csharp
// Salve o documento modificado
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.
  
### Exemplo de código-fonte para Clone Complete Table usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Clone a tabela e insira-a no documento após o original.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Insira um parágrafo vazio entre as duas tabelas,
	// caso contrário, eles serão combinados em um só ao salvar. Isso tem a ver com a validação do documento.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Conclusão
Neste tutorial, aprendemos como clonar uma tabela inteira em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode clonar tabelas em seus documentos do Word programaticamente. Este recurso permite realizar manipulações avançadas em arrays para atender às suas necessidades específicas.