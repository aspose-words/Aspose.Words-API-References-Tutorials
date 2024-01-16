---
title: Enumerar propriedades
linktitle: Enumerar propriedades
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para enumerar propriedades de documentos com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-properties/enumerate-properties/
---

Neste tutorial, orientaremos você no código-fonte C# para enumerar propriedades do documento com Aspose.Words for .NET. Este recurso permite acessar propriedades integradas e personalizadas de um documento.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento Word cujas propriedades queremos listar. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: enumerando propriedades

Agora vamos listar as propriedades do documento, tanto propriedades integradas quanto personalizadas. Use o seguinte código:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Este código exibe o nome do documento e lista as propriedades integradas e personalizadas exibindo seu nome e valor.

### Exemplo de código-fonte para Enumerar Propriedades usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como enumerar propriedades de documentos usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode acessar e visualizar facilmente as propriedades de seus próprios documentos.

