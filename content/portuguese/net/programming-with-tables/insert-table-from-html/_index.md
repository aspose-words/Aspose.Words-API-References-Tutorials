---
title: Inserir tabela de HTML
linktitle: Inserir tabela de HTML
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir uma tabela HTML em um documento Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/insert-table-from-html/
---

Neste tutorial, aprenderemos como inserir uma tabela em um documento Word a partir de HTML usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você será capaz de inserir tabelas de HTML em seus documentos do Word de forma programática.

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

## Etapa 3: Inserindo a tabela do HTML
seguir, inseriremos a tabela no documento usando o código HTML. Use o seguinte código:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Aqui usamos o`InsertHtml` método do construtor de documentos para inserir o HTML que contém a tabela. O HTML especificado cria uma tabela com duas linhas e duas células em cada linha. Você pode personalizar o conteúdo da tabela modificando o código HTML de acordo com suas necessidades.

## Passo 4: Salvando o documento modificado
Por fim, precisamos salvar o documento modificado com a tabela inserida do HTML. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para inserir tabela de HTML usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Observe que AutoFitSettings não se aplica a tabelas inseridas de HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Conclusão
Neste tutorial, aprendemos como inserir uma tabela em um documento Word a partir de HTML usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode inserir tabelas de HTML em seus documentos do Word programaticamente. Este recurso permite converter e importar dados tabulares de fontes HTML para seus documentos do Word.
