---
title: Reduza o tamanho do PDF com a escala de fontes Wmf para o tamanho do metarquivo
linktitle: Reduza o tamanho do PDF com a escala de fontes Wmf para o tamanho do metarquivo
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para reduzir o tamanho do PDF com escala de fontes wmf para o tamanho do metarquivo ao converter para PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Este artigo fornece um guia passo a passo sobre como reduzir o tamanho do PDF com o recurso dimensionar fontes wmf para tamanho de metarquivo com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial, você entenderá como ativar ou desativar o dimensionamento de fonte WMF ao converter para PDF.

Antes de começar, certifique-se de ter instalado e configurado a biblioteca Aspose.Words for .NET em seu projeto. Você pode encontrar a biblioteca e as instruções de instalação no site do Aspose.

## Passo 1: Defina o diretório do documento

 Para começar, você precisa definir o caminho para o diretório onde seus documentos estão localizados. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregue o documento

seguir, precisamos carregar o documento que queremos processar. Neste exemplo, presumimos que o documento se chama "WMF com text.docx" e está localizado no diretório de documentos especificado.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Etapa 3: configurar opções de renderização de metarquivo

 Para ativar ou desativar o dimensionamento da fonte WMF para o tamanho do metarquivo, precisamos configurar o`MetafileRenderingOptions` objeto. Neste exemplo, desabilitamos o dimensionamento da fonte definindo o`ScaleWmfFontsToMetafileSize`propriedade para`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Etapa 4: configurar opções de salvar como PDF com opções de renderização de metarquivo

Finalmente, podemos configurar as opções de salvar em PDF usando as opções de renderização de metarquivo configuradas anteriormente.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Etapa 5: Salvar o documento como PDF com opções de renderização de metarquivo

Salve o documento em formato PDF usando as opções de salvamento configuradas anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Isso é tudo ! Você ativou ou desativou com êxito o dimensionamento da fonte WMF para o tamanho do metarquivo ao converter

um documento PDF usando Aspose.Words for .NET.

### Exemplo de código-fonte para dimensionar fontes WMF para tamanho de metarquivo com Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//Se o Aspose.Words não puder renderizar corretamente alguns dos registros do metarquivo em gráficos vetoriais
	// então Aspose.Words renderiza esse metarquivo em um bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Conclusão

Neste tutorial, explicamos como ativar ou desativar o redimensionamento de fontes WMF para o tamanho do metarquivo em um documento PDF usando Aspose.Words for .NET. Seguindo as etapas descritas, você pode controlar facilmente se as fontes WMF devem ser redimensionadas para corresponder ao tamanho do metarquivo ao converter para um documento PDF. Isso pode ajudá-lo a reduzir o tamanho do arquivo PDF gerado e melhorar o desempenho de renderização. Certifique-se de especificar o caminho correto para seus documentos e configurar as opções de renderização de metarquivo conforme necessário.

### perguntas frequentes

#### P: O que é redimensionar fontes WMF para o tamanho do metarquivo em um documento PDF?
R: Redimensionar fontes WMF para o tamanho do metarquivo em um documento PDF é um recurso que controla se as fontes WMF devem ser dimensionadas para corresponder ao tamanho do metarquivo ao converter para um documento PDF. Quando esse recurso está ativado, as fontes WMF são dimensionadas para corresponder ao tamanho do metarquivo, o que pode reduzir o tamanho do documento PDF gerado.

#### P: Como posso usar o Aspose.Words for .NET para ativar ou desativar o redimensionamento de fontes WMF para o tamanho do metarquivo em um documento PDF?
R: Para ativar ou desativar o redimensionamento de fontes WMF para o tamanho do metarquivo em um documento PDF usando Aspose.Words for .NET, siga estas etapas:

 Defina o caminho do diretório onde seus documentos estão localizados, substituindo`"YOUR DOCUMENT DIRECTORY"` com o caminho real do seu diretório de documentos.

 Carregue o documento que deseja processar usando o`Document` class e especifique o caminho para o documento do Word no diretório de documentos especificado.

 Configure opções de renderização de metarquivo criando uma instância do`MetafileRenderingOptions` classe e definir o`ScaleWmfFontsToMetafileSize`propriedade para`true` para ativar o dimensionamento de fontes WMF para o tamanho do metarquivo ou para`false` para desativar esse recurso.

 Configure as opções de salvar como PDF criando uma instância do arquivo`PdfSaveOptions` class e usando as opções de renderização de metarquivo configuradas anteriormente.

 Salve o documento em formato PDF usando o`Save` método do`Document` classe especificando o caminho e as opções de salvamento.

#### P: Quais são os benefícios de redimensionar fontes WMF para o tamanho do metarquivo em um documento PDF?
R: As vantagens de redimensionar fontes WMF para o tamanho do metarquivo em um documento PDF são:

Redução do tamanho do arquivo PDF: redimensionar fontes WMF para o tamanho do metarquivo pode reduzir o tamanho do documento PDF gerado, adaptando o tamanho da fonte às necessidades do metarquivo.

Desempenho aprimorado: Ao ajustar o tamanho das fontes WMF às dimensões do metarquivo, a renderização do documento PDF pode ser mais rápida e eficiente.