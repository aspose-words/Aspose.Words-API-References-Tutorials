---
title: Definir configuração de página e formatação de seção
linktitle: Definir configuração de página e formatação de seção
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para configurar o layout de um documento e a formatação de seção com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

Neste tutorial, orientaremos você através do código-fonte C# para configurar o layout e a formatação de seção com Aspose.Words for .NET. Este recurso permite definir a orientação da página, as margens e o tamanho do papel.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Criando o documento

Nesta etapa, criaremos um novo documento. Use o código a seguir para criar o documento e inicializar o construtor:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde você deseja salvar o documento.

## Etapa 3: configurar o layout e salvar o documento

Agora vamos configurar o layout do documento. Use o código a seguir para definir a orientação, as margens e o tamanho do papel:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Este código definirá a orientação da página como paisagem, a margem esquerda como 50 e o tamanho do papel como 10x14.

### Exemplo de código-fonte para definir configuração de página e formatação de seção usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

 Certifique-se de especificar o caminho correto para o diretório onde deseja salvar o documento no`dataDir` variável.

Agora você aprendeu como configurar o layout e a formatação de seção de um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode personalizar facilmente o layout e a formatação de seus próprios documentos.