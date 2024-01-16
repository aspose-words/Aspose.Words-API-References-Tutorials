---
title: Escape URI em documento PDF
linktitle: Escape URI em documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo Como escapar de URI em documento PDF com Aspose.Words para .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/escape-uri/
---

Este artigo fornece um guia passo a passo sobre como escapar do URI em um documento PDF com Aspose.Words para .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial, você poderá entender como inserir hiperlinks com Uri de escape em um documento.

Antes de começar, certifique-se de ter instalado e configurado a biblioteca Aspose.Words for .NET em seu projeto. Você pode encontrar a biblioteca e as instruções de instalação no site do Aspose.

## Passo 1: Defina o diretório do documento

 Para começar, você precisa definir o caminho para o diretório onde seus documentos estão localizados. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Crie um documento e um DocumentBuilder

 Em seguida, precisamos criar um novo`Document` objeto e um`DocumentBuilder` objeto para construir o documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: inserir hiperlinks com Uri de escape

 Use o`InsertHyperlink` método do`DocumentBuilder` objeto para inserir hiperlinks no documento. Uri deve ser escapado usando o`Uri.EscapeUriString` função para evitar erros de formatação.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), falso);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), falso);
```

## Etapa 4: salve o documento como PDF

 Finalmente, podemos salvar o documento como PDF usando o`Save` método do`Document` objeto. Especifique o nome do arquivo de saída.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Isso é tudo ! Você inseriu com sucesso hiperlinks com Uri de escape em um documento usando Aspose.Words for .NET.

### Exemplo de código-fonte para Uri escapando com Aspose.Words for .NET


```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", falso);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", falso);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## Conclusão

Neste tutorial, abordamos como escapar de URIs em um documento PDF usando Aspose.Words for .NET. Ao escapar dos URIs, você pode evitar erros de formatação e garantir que os hiperlinks sejam interpretados e exibidos corretamente no documento PDF. Siga as etapas descritas para inserir hiperlinks com URIs de escape em seu documento PDF. Certifique-se de escapar.

### perguntas frequentes

#### P: Qual é o URI de escape em um documento PDF e por que ele é importante?
R: Escape URI em um documento PDF refere-se ao método de conversão de caracteres especiais em uma URL em sequências de escape para evitar erros de formato. Isso é importante porque caracteres especiais em uma URL podem atrapalhar a estrutura da URL e levar a interpretações incorretas ou renderização incorreta. Ao escapar dos caracteres especiais, garantimos que a URL será corretamente interpretada e exibida no documento PDF.

#### P: Como posso usar o Aspose.Words for .NET para escapar de URIs em um documento PDF?
R: Para escapar de URIs em um documento PDF usando Aspose.Words for .NET, siga estas etapas:

 Defina o caminho do diretório onde seus documentos estão localizados, substituindo`"YOUR DOCUMENT DIRECTORY"` com o caminho real do seu diretório de documentos.

 Crie uma nova instância do`Document` aula e um`DocumentBuilder` objeto para construir o documento.

 Use o`InsertHyperlink` método do`DocumentBuilder` objeto para inserir hiperlinks no documento. Certifique-se de escapar do URI usando o`Uri.EscapeUriString` função para evitar erros de formatação.

 Use o`Save` método do`Document` objeto para salvar o documento em formato PDF especificando o nome do arquivo de saída.

#### P: Quais são os benefícios de escapar de URIs em um documento PDF?
R: Os benefícios do escape de URI em um documento PDF são:

Prevenção de erros de formato: o escape de URI ajuda a evitar erros de formato causados por caracteres especiais em uma URL, garantindo que a URL seja interpretada e exibida corretamente no documento PDF.

Compatibilidade com leitores de PDF: URIs com escape geralmente são bem suportados por leitores de PDF, garantindo melhor compatibilidade e uma experiência de usuário consistente.

#### P: Quais caracteres especiais devem ter escape em um URI?
 R: Os caracteres especiais que devem ser escapados em um URI são: espaço, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.