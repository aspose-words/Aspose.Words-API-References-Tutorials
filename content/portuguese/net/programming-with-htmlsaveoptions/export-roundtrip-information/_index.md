---
title: Exportar informações de ida e volta
linktitle: Exportar informações de ida e volta
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para exportar informações de ida e volta ao salvar um documento como HTML com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

Neste tutorial, orientaremos você no código-fonte C# para exportar informações de ida e volta de um documento com Aspose.Words for .NET. Este recurso permite incluir informações de ida e volta no arquivo HTML exportado, facilitando a recuperação das alterações feitas no documento original.

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

Agora vamos configurar as opções de salvamento do HTML para exportar as informações de ida e volta do documento. Use o seguinte código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Este código cria uma instância de`HtmlSaveOptions` define o`ExportRoundtripInformation` opção para`true` para incluir informações de ida e volta ao exportar.

## Passo 4: Convertendo e salvando o documento em HTML

Por fim, converteremos o documento em HTML usando as opções de salvamento de HTML configuradas anteriormente. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Este código converte o documento em HTML, incluindo as informações de ida e volta, e salva o arquivo HTML exportado no diretório especificado.

### Exemplo de código-fonte para exportar informações de ida e volta usando Aspose.Words for .NET


```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Certifique-se de especificar o caminho correto para o diretório de documentos no arquivo`dataDir` variável.