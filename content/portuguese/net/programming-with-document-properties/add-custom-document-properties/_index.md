---
title: Adicionar propriedades personalizadas do documento
linktitle: Adicionar propriedades personalizadas do documento
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para adicionar propriedades personalizadas a um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-properties/add-custom-document-properties/
---

Neste tutorial, orientaremos você no código-fonte C# para adicionar propriedades personalizadas a um documento com Aspose.Words for .NET. Este recurso permite adicionar informações personalizadas ao documento.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa, carregaremos o documento Word ao qual queremos adicionar propriedades personalizadas. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: adicionar propriedades personalizadas

Agora vamos adicionar propriedades personalizadas ao documento. Use o código a seguir para adicionar as propriedades:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Este código primeiro verifica se a propriedade "Autorizado" já existe nas propriedades customizadas. Se existir, o processo é interrompido. Caso contrário, as propriedades customizadas serão adicionadas ao documento.

### Exemplo de código-fonte para adicionar propriedades de documento personalizado usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como adicionar propriedades personalizadas a um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode adicionar facilmente suas próprias propriedades personalizadas aos seus documentos.