---
title: Mostrar erros gramaticais e ortográficos
linktitle: Mostrar erros gramaticais e ortográficos
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para ativar a exibição de erros gramaticais e ortográficos em um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

Neste tutorial, orientaremos você pelo código-fonte C# para permitir a exibição de erros gramaticais e ortográficos com Aspose.Words for .NET. Este recurso permite visualizar erros gramaticais e ortográficos em um documento.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento Word para o qual queremos exibir erros gramaticais e ortográficos. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: ativar exibição de erros

Agora vamos habilitar a exibição de erros gramaticais e ortográficos no documento. Use o seguinte código para ativar a exibição de erros:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Este código permite a exibição de erros gramaticais (`ShowGrammaticalErrors`) e erros ortográficos (`ShowSpellingErrors`) no documento.

### Exemplo de código-fonte para mostrar erros gramaticais e ortográficos usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como habilitar a exibição de erros gramaticais e ortográficos em um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode ativar facilmente esse recurso em seus próprios documentos.