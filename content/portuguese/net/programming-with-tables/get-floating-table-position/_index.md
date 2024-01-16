---
title: Obtenha a posição da mesa flutuante
linktitle: Obtenha a posição da mesa flutuante
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como obter a posição de tabelas flutuantes em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/get-floating-table-position/
---

Neste tutorial, aprenderemos como obter a posição de uma tabela flutuante em um documento Word usando Aspose.Words for .NET. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você poderá obter as propriedades de posicionamento de uma tabela flutuante em seus documentos do Word de forma programática.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento e acessando as tabelas
Para iniciar o Processamento de Palavras com tabelas, precisamos carregar o documento que as contém e acessá-las. Siga esses passos:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos. Além disso, certifique-se de que o documento contenha tabelas flutuantes.

## Etapa 3: obter propriedades de posicionamento da tabela flutuante
A seguir, percorreremos todas as tabelas do documento e obteremos as propriedades de posicionamento da tabela flutuante. Use o seguinte código:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Se a matriz for do tipo flutuante, imprima suas propriedades de posicionamento.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Aqui estamos usando um`foreach` loop para percorrer todas as matrizes no documento. Verificamos se o array é do tipo float verificando o`TextWrapping` propriedade. Nesse caso, imprimimos as propriedades de posicionamento da tabela, como âncora horizontal, âncora vertical, distâncias horizontais e verticais absolutas, permissão de sobreposição, distância horizontal absoluta e alinhamento vertical relativo.
 
### Exemplo de código-fonte para obter posição da tabela flutuante usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Se a tabela for do tipo flutuante, imprima suas propriedades de posicionamento.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Conclusão
Neste tutorial, aprendemos como obter a posição de uma tabela flutuante em um documento Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode obter as propriedades de posicionamento de tabelas flutuantes em seus documentos do Word de forma programática. Este recurso permite analisar e manipular tabelas flutuantes de acordo com suas necessidades específicas.