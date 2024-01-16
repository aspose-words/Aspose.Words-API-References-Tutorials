---
title: Remover informações pessoais
linktitle: Remover informações pessoais
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para remover informações pessoais de um documento com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-properties/remove-personal-information/
---

Neste tutorial, orientaremos você no código-fonte C# para remover informações pessoais de um documento com Aspose.Words for .NET. Este recurso permite remover informações pessoais confidenciais de um documento, como dados de identificação do autor.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa faremos o upload do documento Word do qual queremos remover as informações pessoais. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: excluir informações pessoais

 Agora vamos permitir a remoção de informações pessoais definindo o`RemovePersonalInformation`propriedade para`true`. Use o seguinte código:

```csharp
doc.RemovePersonalInformation = true;
```

Este código ativa a exclusão de informações pessoais do documento.

## Passo 4: Salvando o documento

Por fim, salvaremos o documento com as informações pessoais removidas. Use o seguinte código:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Este código salva o documento com as informações pessoais removidas em um novo arquivo.

### Exemplo de código-fonte para remover informações pessoais usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como remover informações pessoais de um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode remover facilmente informações confidenciais de seus próprios documentos.