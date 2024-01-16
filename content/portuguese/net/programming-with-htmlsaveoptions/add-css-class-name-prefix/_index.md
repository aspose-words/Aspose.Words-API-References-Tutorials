---
title: Adicionar prefixo de nome de classe CSS
linktitle: Adicionar prefixo de nome de classe CSS
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para adicionar um prefixo de nome de classe CSS ao converter um documento para HTML com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

Neste tutorial, orientaremos você no código-fonte C# para adicionar um prefixo de nome de classe CSS com Aspose.Words for .NET. Este recurso permite adicionar um prefixo personalizado aos nomes de classes CSS gerados ao converter um documento para HTML.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento Word que queremos converter para HTML. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: definir opções de salvamento de HTML

Agora vamos definir as opções de salvamento de HTML, incluindo o tipo de folha de estilo CSS e o prefixo do nome da classe CSS. Use o seguinte código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Este código cria uma instância de`HtmlSaveOptions` e conjuntos`CssStyleSheetType` para`CssStyleSheetType.External`para gerar uma folha de estilo CSS externa e`CssClassNamePrefix` para`"pfx_"` prefixar`"pfx_"` para nomear classes CSS.

## Passo 4: Convertendo e salvando o documento em HTML

Finalmente, converteremos o documento em HTML usando as opções de salvamento de HTML definidas anteriormente. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Este código converte o documento em HTML e o salva em um arquivo com o prefixo do nome da classe CSS adicionado.

### Exemplo de código-fonte para adicionar prefixo de nome de classe CSS usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como adicionar um prefixo de nome de classe CSS ao converter um documento em HTML usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode personalizar os nomes das classes CSS em seus documentos HTML convertidos.