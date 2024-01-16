---
title: Converter metarquivos em Emf ou Wmf
linktitle: Converter metarquivos em Emf ou Wmf
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para converter metarquivos para formatos EMF ou WMF ao converter um documento para HTML com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

Neste tutorial, orientaremos você no código-fonte C# para converter metarquivos para o formato EMF ou WMF com Aspose.Words for .NET. Este recurso permite converter imagens em formato metarquivo para formatos mais compatíveis, como EMF ou WMF, ao converter um documento para HTML.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Inserindo uma imagem no documento

Nesta etapa iremos inserir uma imagem no documento a ser convertido. Use o código a seguir para inserir uma imagem de uma fonte de dados usando uma tag HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Este código cria uma instância de`Document` e`DocumentBuilder` para construir o documento. Ele insere um`<img>` tag no documento com uma imagem codificada em base64.

## Etapa 3: definir opções de salvamento de HTML

Agora definiremos as opções de salvamento do HTML, incluindo o formato de metarquivo a ser usado para imagens. Use o seguinte código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Este código cria uma instância de`HtmlSaveOptions` e conjuntos`MetafileFormat` para`HtmlMetafileFormat.EmfOrWmf` para especificar que os metarquivos devem ser convertidos para o formato EMF ou WMF ao converter para HTML.

## Passo 4: Convertendo e salvando o documento em HTML

Por fim converteremos o documento para HTML utilizando as opções de salvar HTML definidas anteriormente. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Este código converte o documento em HTML e o salva em um arquivo com os metarquivos convertidos no formato EMF ou WMF dependendo das opções de salvamento definidas.

### Exemplo de código-fonte para converter metarquivos em Emf ou Wmf usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Certifique-se de especificar o caminho correto para o diretório de documentos no arquivo`dataDir` variável.

Agora você aprendeu como converter metarquivos para formatos EMF ou WMF ao converter um documento para HTML usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode gerenciar facilmente metarquivos em seus documentos HTML convertidos.