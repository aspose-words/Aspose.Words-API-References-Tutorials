---
title: Obter variáveis
linktitle: Obter variáveis
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para recuperar variáveis de documentos com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-document-properties/get-variables/
---

Neste tutorial, orientaremos você no código-fonte C# para recuperar variáveis de um documento com Aspose.Words for .NET. Este recurso permite acessar variáveis definidas em um documento.

## Etapa 1: configuração do projeto

Para começar, crie um novo projeto C# em seu IDE favorito. Certifique-se de que a biblioteca Aspose.Words for .NET seja referenciada em seu projeto.

## Passo 2: Carregando o documento

Nesta etapa carregaremos o documento Word do qual queremos recuperar as variáveis. Use o seguinte código para carregar o documento:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Substituir`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do diretório onde seu documento está localizado.

## Etapa 3: Recuperando variáveis

Agora iremos recuperar as variáveis definidas no documento. Use o seguinte código:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Este código itera sobre cada par de valores-chave nas variáveis do documento e recupera o nome e o valor de cada variável. As variáveis são então concatenadas para exibir as informações de cada variável.

### Exemplo de código-fonte para obter variáveis usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Certifique-se de especificar o caminho correto do documento no`dataDir` variável.

Agora você aprendeu como recuperar variáveis de um documento usando Aspose.Words for .NET. Seguindo o guia passo a passo fornecido neste tutorial, você pode acessar e visualizar facilmente variáveis de seus próprios documentos.