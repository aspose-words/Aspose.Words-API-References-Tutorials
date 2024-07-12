---
title: Configurando link para conteúdo
linktitle: Configurando link para conteúdo
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para configurar links para conteúdo em um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-properties/configuring-link-to-content/
---

Neste tutorial, orientaremos você no código-fonte C# para configurar o link para conteúdo com Aspose.Words for .NET. Este recurso permite vincular a conteúdo específico em um documento.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Etapa 2: Criando o Documento e o Construtor

Nesta etapa criaremos um novo documento e inicializaremos o construtor. Use o seguinte código:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: crie um marcador

Agora criaremos um marcador no documento. Use o código a seguir para criar um marcador com texto dentro:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Este código cria um marcador chamado "MyBookmark" e adiciona algum texto dentro dele.

## Etapa 4: configurar o link de conteúdo

Agora configuraremos o link para o conteúdo usando as propriedades do documento. Use o código a seguir para adicionar e recuperar o link para o conteúdo:

```csharp
// Obtenha a lista de todas as propriedades personalizadas no documento.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Adicione uma propriedade vinculada ao conteúdo.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Este código adiciona uma propriedade relacionada ao conteúdo chamada "Bookmark" com o marcador "MyBookmark". Em seguida, ele recupera informações de propriedade relacionadas ao conteúdo, como status do link, origem do link e valor da propriedade.

### Exemplo de código-fonte para configurar link para conteúdo usando Aspose.Words para .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Recuperar uma lista de todas as propriedades personalizadas do documento do arquivo.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Adicione vinculado à propriedade de conteúdo.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Agora você aprendeu como configurar o link para o conteúdo de um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode criar e configurar facilmente links para conteúdo específico em seus próprios documentos.