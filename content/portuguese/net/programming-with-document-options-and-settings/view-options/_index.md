---
title: Ver opções
linktitle: Ver opções
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para configurar opções de exibição de documentos com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-options-and-settings/view-options/
---

Neste tutorial, orientaremos você no código-fonte C# para configurar as opções de exibição com Aspose.Words for .NET. Este recurso permite personalizar o modo de visualização e o nível de zoom em um documento.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento Word para o qual queremos configurar as opções de exibição. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: configurar opções de exibição

Agora iremos configurar as opções de exibição do documento. Use o código a seguir para definir o modo de exibição e o nível de zoom:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Este código define o modo de visualização como "PageLayout" e o nível de zoom como 50%.

### Exemplo de código-fonte para opções de visualização usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como configurar as opções de exibição de documentos usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode personalizar facilmente a exibição de seus próprios documentos.