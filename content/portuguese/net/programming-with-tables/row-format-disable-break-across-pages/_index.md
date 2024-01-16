---
title: Formato de linha desabilita quebra entre páginas
linktitle: Formato de linha desabilita quebra entre páginas
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como desabilitar a quebra de linha para uma tabela em várias páginas em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/row-format-disable-break-across-pages/
---

Neste tutorial, aprenderemos como desabilitar a quebra de linha de uma tabela de várias páginas em um documento do Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você poderá desabilitar a quebra de linha para todas as linhas da sua tabela em seus documentos do Word.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento
Para iniciar o processamento de palavras com o documento, siga estas etapas:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos e forneça o nome de arquivo correto.

## Etapa 3: desativar a quebra de linha da tabela
A seguir, desabilitaremos a quebra de linha para todas as linhas da tabela. Use o seguinte código:

```csharp
// Recuperar a tabela
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Desativar quebra de linha para todas as linhas da tabela
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Aqui usamos o documento para buscar a primeira tabela e então iterar por todas as linhas da tabela usando um loop foreach. Dentro do loop, desabilitamos a quebra de linha para cada linha definindo o`RowFormat.AllowBreakAcrossPages`propriedade para`false`.

## Passo 4: Salvando o documento modificado
Finalmente, precisamos salvar o documento modificado com a quebra de linha da tabela desabilitada. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para formato de linha desabilitar quebra entre páginas usando Aspose.Words for .NET 

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Desative a quebra de páginas para todas as linhas da tabela.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusão
Neste tutorial, aprendemos como desabilitar a quebra de linha de uma tabela de várias páginas em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode aplicar essa desativação às tabelas em seus documentos do Word.