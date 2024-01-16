---
title: Atualizar dados de favoritos em documento do Word
linktitle: Atualizar dados de favoritos
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para explicar o código-fonte C# da atualização de dados de marcadores Aspose.Words no recurso de documento Word para .NET.
type: docs
weight: 10
url: /pt/net/programming-with-bookmarks/update-bookmark-data/
---

Neste tutorial, percorreremos um guia passo a passo para compreender e implementar o recurso Atualizar dados de marcadores em documento do Word do Aspose.Words for .NET. Este recurso permite atualizar o conteúdo e as propriedades dos marcadores em um documento do Word usando código-fonte C#.

## Requisitos

Antes de prosseguir com o tutorial, certifique-se de ter os seguintes requisitos em vigor:

- Biblioteca Aspose.Words para .NET instalada
- Conhecimento básico da linguagem de programação C#
- Visual Studio ou qualquer outro IDE compatível

## Passo 1: Carregue o documento

Nesta etapa carregaremos o documento Word que contém os favoritos que queremos atualizar. Supondo que você tenha o documento armazenado em um diretório específico, use o seguinte código para carregar o documento:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Passo 2: Acesse o marcador

Para atualizar os dados do marcador, primeiro precisamos acessar o marcador específico no documento. Cada marcador possui um nome exclusivo associado a ele. Use o seguinte código para acessar um marcador chamado "MyBookmark1":

```csharp
Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];
```

Certifique-se de que o nome do marcador corresponda ao do seu documento. Você pode modificá-lo conforme sua necessidade.

## Etapa 3: atualizar as propriedades e o conteúdo dos favoritos

Depois de acessar o marcador, você poderá atualizar suas propriedades e conteúdo. No trecho de código a seguir, atualizaremos o nome e o texto do marcador:

```csharp
string name = bookmark.Name;
string text = bookmark.Text;

bookmark.Name = "RenamedBookmark";
bookmark.Text = "This is a new bookmarked text.";
```

Você pode personalizar o nome do marcador e o novo texto de acordo com suas necessidades. O código acima renomeia o marcador para “RenamedBookmark” e atualiza o conteúdo do texto.

## Etapa 4: salve o documento atualizado

Após atualizar os dados do marcador, você precisa salvar o documento modificado. Use o seguinte código para salvar o documento:

```csharp
doc.Save(dataDir + "UpdatedDocument.docx");
```

Este código salvará o documento modificado com o nome “UpdatedDocument.docx” no mesmo diretório do documento original.

### Exemplo de código-fonte para atualizar dados de favoritos usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];

	string name = bookmark.Name;
	string text = bookmark.Text;

	bookmark.Name = "RenamedBookmark";
	bookmark.Text = "This is a new bookmarked text.";

```

 Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Conclusão

Parabéns! Você aprendeu com sucesso como atualizar dados de favoritos usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, agora você poderá incorporar esse recurso em seus aplicativos C# e manipular marcadores em documentos do Word de maneira programática.

### Perguntas frequentes para atualizar dados de favoritos em documentos do Word

#### P: O recurso de atualização de dados de marcadores funciona apenas com marcadores em documentos do Word?

R: Sim, o recurso Atualizar dados de marcadores foi projetado especificamente para marcadores em documentos do Word. Permite atualizar o conteúdo e as propriedades dos marcadores em um documento do Word.

#### P: Posso atualizar outras propriedades de marcadores além do texto?

 R: Sim, além do texto, você também pode atualizar outras propriedades do marcador, como nome do marcador, escopo do marcador, etc.`Bookmark` objeto para atualizar as propriedades desejadas.

#### P: Posso atualizar vários marcadores no mesmo documento?

R: Sim, você pode atualizar vários marcadores no mesmo documento repetindo as etapas de acesso e atualização para cada marcador. Certifique-se de usar nomes de marcadores exclusivos para cada marcador que deseja atualizar.

#### P: A função de atualização de dados do marcador modifica o documento original?

R: Sim, o recurso de atualização de dados do marcador modifica o documento original atualizando as propriedades e o conteúdo do marcador. Certifique-se de salvar uma cópia do documento original antes de aplicar este recurso.