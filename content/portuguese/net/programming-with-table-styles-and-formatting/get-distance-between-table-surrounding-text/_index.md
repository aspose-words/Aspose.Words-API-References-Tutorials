---
title: Obtenha distância entre o texto ao redor da tabela
linktitle: Obtenha distância entre o texto ao redor da tabela
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para obter a distância entre o texto e uma tabela em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

Neste tutorial, orientaremos você no processo passo a passo para obter a distância entre o texto ao redor em uma tabela usando Aspose.Words for .NET. Explicaremos o código-fonte C# incluído e forneceremos um guia completo para ajudá-lo a entender e implementar esse recurso em seus próprios projetos. Ao final deste tutorial, você saberá como acessar as diversas distâncias entre uma tabela e o texto ao redor em seus documentos Word usando Aspose.Words for .NET.

## Passo 1: Defina o diretório do documento
Primeiro, você precisa definir o caminho para o diretório de documentos. É aqui que o seu documento do Word está localizado. Substitua "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: carregar o documento existente
 Em seguida, você precisa carregar o documento Word existente em uma instância do`Document` aula.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Etapa 3: obtenha a distância entre a tabela e o texto ao redor
 Para obter a distância entre a tabela e o texto ao redor, precisamos acessar a tabela no documento usando o`GetChild()` método e o`NodeType.Table` propriedade. Podemos então exibir as diferentes distâncias usando as propriedades do array`DistanceTop`, `DistanceBottom`, `DistanceRight`e`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Exemplo de código-fonte para obter distância entre o texto circundante da tabela usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Conclusão
Neste tutorial, aprendemos como obter a distância entre o texto circundante em uma tabela usando Aspose.Words for .NET. Seguindo este guia passo a passo, você pode acessar facilmente as várias distâncias entre uma tabela e o texto ao redor em seus documentos do Word. Aspose.Words oferece uma API poderosa e flexível para manipular e formatar tabelas em seus documentos. Com esse conhecimento, você poderá analisar o layout de suas tabelas em relação ao texto e atender necessidades específicas.