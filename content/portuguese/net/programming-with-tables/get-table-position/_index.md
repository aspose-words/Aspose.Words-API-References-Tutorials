---
title: Obter posição na mesa
linktitle: Obter posição na mesa
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como obter a posição de uma tabela em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/get-table-position/
---

Neste tutorial, aprenderemos como obter a posição de uma tabela em um documento Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você poderá obter propriedades de posicionamento de tabelas em seus documentos do Word de forma programática.

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

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos. Além disso, certifique-se de que o documento contenha a tabela cuja posição você deseja obter.

## Etapa 3: Obtendo propriedades de posicionamento de array
A seguir, verificaremos o tipo de posicionamento do array e obteremos as propriedades de posicionamento apropriadas. Use o seguinte código:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Aqui usamos uma condição para verificar se o array é do tipo float. Se sim, imprimimos o`RelativeHorizontalAlignment`e`RelativeVerticalAlignment` propriedades para obter o alinhamento horizontal e vertical relativo da tabela. Caso contrário, imprimimos o`Alignment` propriedade para obter o alinhamento da matriz.

### Exemplo de código-fonte para obter posição da tabela usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Conclusão
Neste tutorial, aprendemos como obter a posição de uma tabela em um documento Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode obter propriedades de posicionamento de tabela em seus documentos do Word de forma programática. Este recurso permite analisar e manipular arrays de acordo com suas posições específicas.