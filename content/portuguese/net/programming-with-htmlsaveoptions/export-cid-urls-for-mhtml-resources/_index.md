---
title: Exportar URLs Cid para recursos Mhtml
linktitle: Exportar URLs Cid para recursos Mhtml
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para exportar URLs CID de recursos MHTML ao salvar um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

Neste tutorial, orientaremos você no código-fonte C# para exportar URLs CID para recursos MHTML com Aspose.Words for .NET. Este recurso permite exportar URLs CID de recursos MHTML ao salvar um documento no formato MHTML.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento para exportar. Use o código a seguir para carregar o documento de um diretório especificado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Este código cria uma instância de`Document` carregando o documento do diretório especificado.

## Etapa 3: configurar opções de backup HTML

Agora configuraremos as opções de salvamento de HTML para exportar URLs CID de recursos MHTML. Use o seguinte código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Este código cria uma instância de`HtmlSaveOptions` com o formato de salvamento definido como MHTML. Também permite a exportação de URLs CID de recursos MHTML configurando`ExportCidUrlsForMhtmlResources` para`true`.

## Passo 4: Convertendo e salvando o documento em MHTML

Por fim, converteremos o documento para MHTML usando as opções de salvamento de HTML configuradas anteriormente. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Este código converte o documento em MHTML e o salva em um arquivo com as URLs CID dos recursos MHTML exportados.

### Exemplo de código-fonte para exportar URLs Cid para recursos Mhtml usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Certifique-se de especificar o caminho correto para o diretório de documentos no arquivo`dataDir` variável.

Agora você aprendeu como exportar URLs CID de recursos MHTML ao salvar um documento no formato MHTML usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode gerenciar facilmente URLs CID em seus documentos MHTML exportados.

