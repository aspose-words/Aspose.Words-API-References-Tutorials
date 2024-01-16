---
title: Remover propriedades personalizadas do documento
linktitle: Remover propriedades personalizadas do documento
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para remover propriedades personalizadas de um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-properties/remove-custom-document-properties/
---

Neste tutorial, orientaremos você no código-fonte C# para remover propriedades personalizadas de um documento com Aspose.Words for .NET. Este recurso permite remover uma propriedade personalizada específica de um documento.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa, carregaremos o documento Word do qual queremos remover as propriedades personalizadas. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: excluir propriedades personalizadas

Agora vamos remover uma propriedade personalizada específica do documento. Use o seguinte código:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Este código remove a propriedade customizada "Data Autorizada" do documento. Você pode substituir "Data de autorização" pelo nome da propriedade personalizada que deseja remover.

### Exemplo de código-fonte para remover propriedades personalizadas do documento usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como remover propriedades personalizadas de um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode remover facilmente propriedades personalizadas de seus próprios documentos.