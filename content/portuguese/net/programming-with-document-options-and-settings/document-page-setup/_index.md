---
title: Configuração da página do documento
linktitle: Configuração da página do documento
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para configurar um layout de documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-options-and-settings/document-page-setup/
---

Neste tutorial, orientaremos você no código-fonte C# para configurar o layout do documento com Aspose.Words for .NET. Este recurso permite definir o modo de layout, o número de caracteres por linha e o número de linhas por página.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento Word que queremos configurar. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: configurando o layout

Agora vamos configurar o layout do documento. Use o código a seguir para definir o modo de layout, o número de caracteres por linha e o número de linhas por página:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Este código define o modo de layout como "Grade" e especifica o número de caracteres por linha e o número de linhas por página.

### Exemplo de código-fonte para configuração de página de documento usando Aspose.Words for .NET


```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Defina o modo de layout de uma seção permitindo definir o comportamento da grade do documento.
	// Observe que a guia Grade do documento fica visível na caixa de diálogo Configuração de página do MS Word
	// se algum idioma asiático for definido como idioma de edição.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como configurar o layout de um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode personalizar facilmente o layout de seus próprios documentos.