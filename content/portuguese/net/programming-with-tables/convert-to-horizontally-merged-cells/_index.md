---
title: Converter em células mescladas horizontalmente
linktitle: Converter em células mescladas horizontalmente
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como converter células de tabela em células mescladas horizontalmente em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

Neste tutorial, aprenderemos como usar Aspose.Words for .NET para converter células de tabela em células mescladas horizontalmente em um documento do Word. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você será capaz de manipular células de tabelas em seus documentos do Word de forma programática.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento e acessando a tabela
Para iniciar o Processamento de Palavras com a tabela, precisamos carregar o documento que a contém e acessá-lo. Siga esses passos:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Acesso à matriz
Table table = doc.FirstSection.Body.Tables[0];
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos. Além disso, certifique-se de que o documento contenha uma tabela com células mescladas horizontalmente.

## Etapa 3: converter em células mescladas horizontalmente
 A seguir, converteremos as células da tabela em células mescladas horizontalmente usando o`ConvertToHorizontallyMergedCells()` método. Use o seguinte código:

```csharp
// Converter em células mescladas horizontalmente
table. ConvertToHorizontallyMergedCells();
```

 Aqui nós apenas chamamos o`ConvertToHorizontallyMergedCells()` método na matriz para realizar a conversão.

### Exemplo de código-fonte para converter em células mescladas horizontalmente usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Agora as células mescladas possuem sinalizadores de mesclagem apropriados.
	table.ConvertToHorizontallyMergedCells();
```

## Conclusão
Neste tutorial, aprendemos como converter células de tabela em células mescladas horizontalmente em um documento do Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode manipular células de tabela em seus documentos do Word de forma programática. Este recurso permite gerenciar e organizar seus dados de forma flexível e personalizada em uma tabela.