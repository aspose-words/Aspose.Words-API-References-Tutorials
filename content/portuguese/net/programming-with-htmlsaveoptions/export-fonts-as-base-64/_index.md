---
title: Exportar fontes como base 64
linktitle: Exportar fontes como base 64
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para exportar fontes de base 64 ao salvar um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

Neste tutorial, orientaremos você no código-fonte C# para exportar fontes base 64 com Aspose.Words for .NET. Este recurso permite exportar fontes como dados de base 64 ao salvar um documento no formato HTML.

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

Agora vamos configurar as opções de salvamento de HTML para exportar fontes de base 64. Use o seguinte código:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Este código cria uma instância de`HtmlSaveOptions` e conjuntos`ExportFontsAsBase64` para`true` para especificar que as fontes devem ser exportadas como dados de base 64 ao salvar como HTML.

## Passo 4: Convertendo e salvando o documento em HTML

Por fim, converteremos o documento em HTML usando as opções de salvamento de HTML configuradas anteriormente. Use o seguinte código:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Este código converte o documento em HTML e o salva em um arquivo com as fontes exportadas como dados de base 64.

### Exemplo de código-fonte para exportar fontes como Base 64 usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Certifique-se de especificar o caminho correto para o diretório de documentos no arquivo`dataDir` variável.

Agora você aprendeu como exportar fontes de base 64 ao salvar um documento como HTML usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode exportar facilmente fontes de forma segura e incorporadas em seus documentos HTML.