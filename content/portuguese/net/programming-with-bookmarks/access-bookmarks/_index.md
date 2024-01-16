---
title: Acessar marcadores em documento do Word
linktitle: Acessar marcadores em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como acessar marcadores em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/access-bookmarks/
---

Neste artigo, exploraremos o código-fonte C# acima para entender como usar a função Access Bookmarks na biblioteca Aspose.Words for .NET. Este recurso fornece acesso a marcadores específicos em um documento do Word.

## Pré-requisitos

- Conhecimento básico da linguagem C#.
- Ambiente de desenvolvimento .NET com biblioteca Aspose.Words instalada.

## Passo 1: Carregando o documento

 Antes de começarmos a acessar os favoritos, precisamos carregar um documento do Word usando Aspose.Words for .NET. Isso pode ser feito instanciando um`Document` objeto especificando o caminho do arquivo do documento:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Passo 2: Acesso aos favoritos

Assim que o documento for carregado, podemos acessar os marcadores do documento. Existem duas maneiras de acessar os favoritos: por índice e por nome.

- Acesso por índice: No nosso exemplo, utilizamos o índice 0 para acessar o primeiro marcador do documento:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Acesso por nome: Em nosso exemplo, utilizamos o nome “MyBookmark3” para acessar um marcador específico no documento:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Exemplo de código-fonte para marcadores de acesso usando Aspose.Words for .NET

Aqui está o exemplo de código-fonte completo para demonstrar o acesso a marcadores usando Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// Por índice:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// Por nome:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Conclusão

Neste artigo, exploramos o código-fonte C# para entender como usar o recurso Access Bookmarks do Aspose.Words for .NET. Seguimos um guia passo a passo para fazer upload de um documento e acessar os favoritos usando índice e nome.

### Perguntas frequentes para acessar marcadores em documentos do Word

#### P: Como posso fazer upload de um documento do Word usando Aspose.Words for .NET?

 R: Para carregar um documento do Word usando Aspose.Words for .NET, você pode instanciar um`Document`objeto especificando o caminho do arquivo do documento. Aqui está um exemplo de código:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

#### P: Como posso acessar os favoritos em um documento do Word?

 R: Você pode acessar marcadores em um documento do Word usando o`Bookmarks` propriedade do`Range` objeto. Você pode acessar os favoritos por índice ou por nome. Aqui está um exemplo de código:

- Acesso por índice:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Acesso por nome:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

#### P: Qual biblioteca é necessária para usar o recurso de acesso a marcadores no Aspose.Words for .NET?

R: Para usar o recurso de acesso a marcadores no Aspose.Words for .NET, você precisa da biblioteca Aspose.Words. Certifique-se de ter esta biblioteca instalada em seu ambiente de desenvolvimento .NET.

#### P: Existem outras maneiras de acessar marcadores em um documento do Word?

 R: Sim, além de acessar os marcadores por índice ou por nome, você também pode percorrer todos os marcadores do documento usando um loop. Você pode obter o número total de marcadores no documento usando o`Count` propriedade do`Bookmarks` coleção. Então você pode acessar cada marcador usando o índice. Aqui está um exemplo de código:

```csharp
int bookmarkCount = doc.Range.Bookmarks.Count;

for (int i = 0; i < bookmarkCount; i++)
{
     Bookmark bookmark = doc.Range.Bookmarks[i];
     // Faça algo com o marcador...
}
```