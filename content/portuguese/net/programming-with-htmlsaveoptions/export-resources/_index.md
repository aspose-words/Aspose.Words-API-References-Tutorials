---
title: Exportar recursos
linktitle: Exportar recursos
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para exportar recursos de documentos ao salvar como HTML com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/export-resources/
---

Neste tutorial, orientaremos você no código-fonte C# para exportar recursos de documentos com Aspose.Words for .NET. Este recurso permite exportar recursos, como fontes, como arquivos externos ao salvar um documento no formato HTML.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento para exportar. Use o código a seguir para carregar o documento de um diretório especificado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Este código cria uma instância de`Document` carregando o documento do diretório especificado.

## Etapa 3: configurar opções de backup HTML

Agora iremos configurar as opções de salvamento de HTML para exportar os recursos do documento. Use o seguinte código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://exemplo.com/recursos"
};
```

 Este código cria uma instância de`HtmlSaveOptions` e define as seguintes opções:

- `CssStyleSheetType` está configurado para`CssStyleSheetType.External`para exportar a folha de estilo CSS para um arquivo externo.
- `ExportFontResources` está configurado para`true` para exportar recursos de fontes.
- `ResourceFolder` especifica o diretório de destino onde os recursos serão salvos.
- `ResourceFolderAlias` especifica o alias de URL que será usado para acessar recursos.

## Passo 4: Convertendo e salvando o documento em HTML

Por fim, converteremos o documento em HTML usando as opções de salvamento de HTML configuradas anteriormente. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Este código converte o documento em HTML e salva os recursos no diretório especificado, usando o alias de URL especificado.

### Exemplo de código-fonte para recursos de exportação usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://exemplo.com/recursos"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Certifique-se de especificar o caminho correto para o diretório de documentos no arquivo`dataDir` variável.