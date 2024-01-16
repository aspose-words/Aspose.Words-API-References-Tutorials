---
title: Compressão de imagem em um documento PDF
linktitle: Compressão de imagem em um documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para compactar imagens em um documento PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/image-compression/
---

Este artigo fornece um guia passo a passo sobre como usar o recurso Compactação de imagem em um documento PDF com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial você poderá entender como compactar imagens em um documento e gerar um PDF com compactação de imagem adequada.

Antes de começar, certifique-se de ter instalado e configurado a biblioteca Aspose.Words for .NET em seu projeto. Você pode encontrar a biblioteca e as instruções de instalação no site do Aspose.

## Passo 1: Defina o diretório do documento

 Para começar, você precisa definir o caminho para o diretório onde seus documentos estão localizados. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregue o documento

A seguir, precisamos carregar o documento que queremos processar. Neste exemplo, presumimos que o documento se chama "Rendering.docx" e está localizado no diretório de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Etapa 3: configurar opções de salvar como PDF com compactação de imagem

 Para compactar imagens ao converter para PDF, precisamos configurar o`PdfSaveOptions` objeto. Podemos definir o tipo de compactação de imagem, qualidade JPEG e outras opções de conformidade com PDF, se necessário.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Passo 4: Salve o documento como PDF com compactação de imagem

Por fim, podemos salvar o documento em formato PDF utilizando as opções de salvamento configuradas anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Etapa 5: Configurar opções para salvar em PDF/A-2u com compactação de imagem

Se você deseja gerar PDF compatível com PDF/A-2u com compactação de imagem, você pode configurar as opções adicionais de salvamento.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Use compactação JPEG com qualidade de 50% para reduzir o tamanho do arquivo.
};
```

## Etapa 6: Salve o documento como PDF/A-2u com compactação de imagem

Salve o documento no formato PDF/A-2u usando as opções adicionais de salvamento configuradas anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Isso é tudo ! Você comprimiu com sucesso as imagens em um documento e gerou um PDF com compactação de imagem adequada usando Aspose.Words for .NET.

### Exemplo de código-fonte para compactação de imagens com Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Use compactação JPEG com qualidade de 50% para reduzir o tamanho do arquivo.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Conclusão

Neste tutorial, explicamos como compactar imagens em um documento PDF usando Aspose.Words for .NET. Seguindo as etapas descritas, você pode reduzir facilmente o tamanho das imagens no seu documento PDF e gerar um PDF com compactação de imagem adequada. Use os recursos de compactação de imagem do Aspose.Words for .NET para otimizar o tamanho de seus documentos PDF enquanto preserva a qualidade da imagem.

### perguntas frequentes

#### P: O que é compactação de imagem em um documento PDF?
R: Compactar imagens em um documento PDF reduz o tamanho das imagens incluídas no documento PDF para reduzir o tamanho geral do arquivo PDF. Isso reduz o espaço de armazenamento necessário e melhora o desempenho ao carregar e visualizar o PDF.

#### P: Como posso compactar imagens em um documento PDF com Aspose.Words for .NET?
R: Para compactar imagens em um documento PDF com Aspose.Words for .NET, siga estas etapas:

 Crie uma instância do`Document` classe especificando o caminho para o documento do Word.

 Crie uma instância do`PdfSaveOptions` classe e definir o`ImageCompression`propriedade para`PdfImageCompression.Jpeg` para usar compactação JPEG.

Você também pode definir outras opções de compactação de imagem, como qualidade JPEG, de acordo com suas necessidades.

 Use o`Save` método do`Document`class para salvar o documento em formato PDF especificando opções de salvamento.

#### P: Qual é a diferença entre a compactação de imagem padrão e a compactação de imagem PDF/A-2u?
R: A compactação de imagem padrão reduz o tamanho das imagens em um documento PDF enquanto preserva os campos do formulário. Isso reduz o tamanho geral do arquivo PDF sem comprometer a funcionalidade do campo do formulário.

compactação de imagem com PDF/A-2u é uma opção adicional que permite gerar um arquivo PDF em conformidade com o padrão PDF/A-2u ao aplicar a compactação de imagem. PDF/A-2u é um padrão ISO para arquivamento de documentos PDF e garante a preservação de documentos a longo prazo.
