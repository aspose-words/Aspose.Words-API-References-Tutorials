---
title: Carregar PDF criptografado
linktitle: Carregar PDF criptografado
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para carregar um PDF criptografado usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

Ao processar palavras com documentos PDF em seu aplicativo .NET, pode ser necessário carregar arquivos PDF protegidos por senha. Aspose.Words for .NET é uma biblioteca poderosa que fornece funcionalidade para carregar documentos PDF criptografados. Neste artigo, iremos guiá-lo passo a passo para compreender e usar esse recurso.

## Compreendendo o recurso Carregar PDF criptografado

recurso Carregar PDF criptografado do Aspose.Words for .NET permite carregar arquivos PDF protegidos por senha. Você pode especificar a senha ao carregar o documento para poder acessar seu conteúdo e manipulá-lo conforme necessário.

## Passo 1: Carregando o Documento PDF Criptografado

A primeira etapa é carregar o documento PDF criptografado em seu aplicativo. Veja como fazer isso:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Certifique-se de especificar o caminho correto para o arquivo PDF criptografado no`dataDir` variável.

## Passo 2: Criptografando o Documento PDF

 Se você também deseja criptografar seu documento PDF, você pode fazer isso usando o`PdfSaveOptions` classe e especificando os detalhes de criptografia:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Isto criará uma versão criptografada do documento PDF no diretório especificado.

## Passo 3: Salvando o Documento PDF Criptografado

Depois de carregar e criptografar opcionalmente o documento PDF, você pode salvá-lo em outro formato ou processá-lo posteriormente de acordo com suas necessidades específicas.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Etapa 5: Carregando o documento PDF criptografado com senha

Manutenção

No entanto, se quiser carregar o documento PDF criptografado com uma senha, você deve usar o`PdfLoadOptions` class e especifique a senha ao carregar o documento:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Certifique-se de fornecer a senha correta no`Password` variável.

### Exemplo de código-fonte para carregar PDF criptografado usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Conclusão

Neste artigo, exploramos como usar o recurso Carregar PDF criptografado do Aspose.Words for .NET. Você aprendeu como fazer upload de arquivos PDF criptografados, como criptografar um documento PDF, como fazer upload de um PDF criptografado com senha e como gerar saída no formato Markdown. Este recurso é extremamente útil no processamento de palavras com documentos PDF seguros.


