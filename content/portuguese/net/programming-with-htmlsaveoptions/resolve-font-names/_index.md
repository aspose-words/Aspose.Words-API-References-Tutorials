---
title: Resolver nomes de fontes
linktitle: Resolver nomes de fontes
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para resolver nomes de fontes ausentes ao converter para HTML com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/resolve-font-names/
---

Neste tutorial, orientaremos você no código-fonte C# para resolver nomes de fontes ausentes com Aspose.Words for .NET. Este recurso permite resolver automaticamente nomes de fontes ausentes ao converter um documento em HTML.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento a ser processado. Use o código a seguir para carregar o documento de um diretório especificado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Este código cria uma instância de`Document` carregando o documento do diretório especificado.

## Etapa 3: configurar opções de backup HTML

Agora configuraremos as opções de salvamento de HTML para resolver nomes de fontes ausentes durante a conversão. Use o seguinte código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Este código cria uma instância de`HtmlSaveOptions` define o`ResolveFontNames` opção para`true`para resolver nomes de fontes ausentes ao converter para HTML. Também o`PrettyFormat` opção está definida como`true` para obter um código HTML bem formatado.

## Passo 4: Convertendo e salvando o documento em HTML

Por fim, converteremos o documento em HTML usando as opções de salvamento de HTML configuradas anteriormente. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Este código converte o documento em HTML resolvendo automaticamente nomes de fontes ausentes e salva o arquivo HTML convertido no diretório especificado.

### Exemplo de código-fonte para resolver nomes de fontes usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Certifique-se de especificar o caminho correto para o diretório de documentos no arquivo`dataDir` variável.