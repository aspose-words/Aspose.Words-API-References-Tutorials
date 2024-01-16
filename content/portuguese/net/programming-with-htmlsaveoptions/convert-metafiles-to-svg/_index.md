---
title: Converter metarquivos em SVG
linktitle: Converter metarquivos em SVG
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para converter metarquivos para o formato SVG ao converter um documento para HTML com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

Neste tutorial, orientaremos você no código-fonte C# para converter metarquivos para o formato SVG com Aspose.Words for .NET. Este recurso permite converter metarquivos para o formato SVG ao converter um documento para HTML.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Inserindo uma imagem SVG no documento

Nesta etapa iremos inserir uma imagem SVG no documento a ser convertido. Use o código a seguir para inserir uma imagem SVG usando uma tag HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Este código cria uma instância de`Document` e`DocumentBuilder` para construir o documento. Ele insere um`<svg>` etiqueta contendo um`<polygon>` elemento com atributos para definir a forma e o estilo da imagem SVG.

## Etapa 3: definir opções de salvamento de HTML

Agora definiremos as opções de salvamento do HTML, especificando que os metarquivos devem ser convertidos para o formato SVG. Use o seguinte código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Este código cria uma instância de`HtmlSaveOptions` e conjuntos`MetafileFormat` para`HtmlMetafileFormat.Svg` para especificar que os metarquivos devem ser convertidos para o formato SVG ao converter para HTML.

## Passo 4: Convertendo e salvando o documento em HTML

Finalmente, converteremos o documento em HTML usando as opções de salvamento de HTML definidas anteriormente. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Este código converte o documento para HTML e o salva em um arquivo com os metarquivos convertidos para SVG.

### Exemplo de código-fonte para converter metarquivos em Svg usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
