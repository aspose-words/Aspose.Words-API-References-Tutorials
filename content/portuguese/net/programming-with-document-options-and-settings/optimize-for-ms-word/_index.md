---
title: Otimizar para Ms Word
linktitle: Otimizar para Ms Word
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para otimizar um documento para MS Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-options-and-settings/optimize-for-ms-word/
---

Neste tutorial, orientaremos você através do código-fonte C# para otimizar um documento para MS Word com Aspose.Words for .NET. Este recurso permite otimizar um documento para uma versão específica do MS Word.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento Word que queremos otimizar. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: Otimização para MS Word

Agora vamos otimizar o documento para uma versão específica do MS Word. Use o seguinte código para realizar a otimização:

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2016);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
```

 Este código diz ao Aspose.Words para otimizar o documento para MS Word 2016. Você pode substituir`MsWordVersion.Word2016` com a versão específica do MS Word que você deseja otimizar.

### Exemplo de código-fonte para Optimize For Ms Word usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2016);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
   
```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como otimizar um documento para uma versão específica do MS Word usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode otimizar facilmente seus próprios documentos para diferentes versões do MS Word.