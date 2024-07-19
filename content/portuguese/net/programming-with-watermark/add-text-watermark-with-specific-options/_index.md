---
title: Adicionar marca d'água de texto com opções específicas
linktitle: Adicionar marca d'água de texto com opções específicas
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como adicionar uma marca d'água de texto com opções específicas usando Aspose.Words for .NET. Guia passo a passo.
type: docs
weight: 10
url: /pt/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

Neste tutorial, orientaremos você sobre como adicionar uma marca d'água de texto com opções específicas usando Aspose.Words for .NET. Uma marca d'água de texto é um texto sobreposto a um documento para indicar que se trata de um rascunho, confidencial, etc.

## Etapa 1: usando um gerador de documentos

Primeiro, usaremos um gerador de documentos para adicionar conteúdo ao nosso documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregando o documento

Carregaremos um documento existente usando o caminho do documento.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Etapa 3: adicionar marca d'água de texto com opções específicas

 Criaremos uma instância do`TextWatermarkOptions`class e defina as opções desejadas para a marca d'água do texto.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Etapa 4: salve o documento

Finalmente, podemos salvar o documento com a marca d’água de texto adicionada.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Exemplo de código-fonte para adicionar marca d'água de texto com opções específicas com Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Parabéns! Agora você aprendeu como adicionar marca d'água de texto com opções específicas usando Aspose.Words for .NET.

