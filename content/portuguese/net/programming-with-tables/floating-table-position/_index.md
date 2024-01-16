---
title: Posição da mesa flutuante
linktitle: Posição da mesa flutuante
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como posicionar uma tabela em uma posição flutuante em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-tables/floating-table-position/
---

Neste tutorial, aprenderemos como usar Aspose.Words for .NET para posicionar uma tabela em uma posição flutuante em um documento Word. Seguiremos um guia passo a passo para entender o código e implementar esse recurso. Ao final deste tutorial, você será capaz de controlar programaticamente a posição e o alinhamento das tabelas flutuantes em seus documentos do Word.

## Etapa 1: configuração do projeto
1. Inicie o Visual Studio e crie um novo projeto C#.
2. Adicione uma referência à biblioteca Aspose.Words for .NET.

## Passo 2: Carregando o documento e acessando a tabela
Para iniciar o Processamento de Palavras com a tabela, precisamos carregar o documento que a contém e acessá-lo. Siga esses passos:

```csharp
// Caminho para o seu diretório de documentos
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carregue o documento
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Acesso à matriz
Table table = doc.FirstSection.Body.Tables[0];
```

Certifique-se de substituir "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho real para o diretório de documentos. Além disso, certifique-se de que o documento contenha uma tabela que será posicionada em posição flutuante.

## Passo 3: Posicionando a placa flutuante
A seguir, posicionaremos a tabela em uma posição flutuante usando as propriedades fornecidas pelo Aspose.Words for .NET. Use o seguinte código:

```csharp
// Posicionando a mesa flutuante
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Aqui usamos o`AbsoluteHorizontalDistance` propriedade para definir a distância horizontal absoluta da tabela da borda esquerda da página. Também usamos o`RelativeVerticalAlignment` propriedade para definir o alinhamento vertical relativo da tabela com o conteúdo circundante.

## Passo 4: Salvando o documento modificado
Por fim, precisamos salvar o documento modificado com a tabela posicionada em posição flutuante. Use o seguinte código:

```csharp
// Salve o documento modificado
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Certifique-se de especificar o caminho e o nome de arquivo corretos para o documento de saída.

### Exemplo de código-fonte para posição de tabela flutuante usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Conclusão
Neste tutorial, aprendemos como posicionar uma tabela em uma posição flutuante em um documento Word usando Aspose.Words for .NET. Seguindo este guia passo a passo e implementando o código C# fornecido, você pode controlar a posição e o alinhamento de tabelas flutuantes em seus documentos do Word de forma programática.