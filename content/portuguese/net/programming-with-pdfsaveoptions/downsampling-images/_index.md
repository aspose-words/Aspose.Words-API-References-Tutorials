---
title: Reduza o tamanho do documento PDF com redução da resolução de imagens
linktitle: Reduza o tamanho do documento PDF com redução da resolução de imagens
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como reduzir o tamanho do documento PDF com redução da resolução de imagens ao converter para PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/downsampling-images/
---

Neste tutorial, orientaremos você nas etapas para reduzir o tamanho do documento PDF com redução da resolução de imagens ao converter para PDF com Aspose.Words for .NET. Isso reduz o tamanho do arquivo PDF gerado. Siga os passos abaixo:

## Passo 1: Carregando o documento

Comece enviando o documento que deseja converter para PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Certifique-se de especificar o caminho correto para o seu documento.

## Passo 2: Configurar opções de salvamento de PDF

Crie uma instância da classe PdfSaveOptions e defina as opções de redução de escala da imagem:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 O`Resolution` propriedade especifica a resolução alvo das imagens e o`ResolutionThreshold` propriedade especifica a resolução mínima abaixo da qual as imagens não serão reduzidas.

## Passo 3: Converter Documento em PDF

 Use o`Save` método para converter o documento em PDF especificando opções de salvamento:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Certifique-se de especificar o caminho correto para salvar o PDF convertido.

### Exemplo de código-fonte para imagens de redução de resolução usando Aspose.Words para .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Podemos definir um limite mínimo para redução da resolução.
	// Este valor impedirá que a segunda imagem no documento de entrada seja reduzida.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Seguindo essas etapas, você pode reduzir facilmente a resolução da imagem ao converter para PDF com Aspose.Words for .NET.

## Conclusão

Neste tutorial, explicamos como reduzir o tamanho de um documento PDF com amostragem de imagem ao converter para PDF usando Aspose.Words for .NET. Seguindo os passos descritos, você pode reduzir facilmente a resolução das imagens e o tamanho do arquivo PDF gerado. Certifique-se de especificar o caminho correto para o seu documento e configurar as opções de amostragem de imagem conforme necessário. A redução do tamanho do arquivo PDF facilita o compartilhamento, o armazenamento e o carregamento rápido do arquivo em diferentes plataformas. Aproveite os benefícios de reduzir o tamanho do documento PDF com amostragem de imagens usando Aspose.Words for .NET.

### perguntas frequentes

#### P: O que é a redução do tamanho do documento PDF com amostragem de imagem?
R: Reduzir o tamanho do documento PDF com Amostragem de Imagem é diminuir o tamanho do arquivo PDF gerado, reduzindo a resolução das imagens ao converter para PDF. Isso otimiza o uso do espaço de armazenamento e facilita o compartilhamento e a transferência do arquivo PDF.

#### P: Como posso reduzir o tamanho do documento PDF com amostragem de imagem usando Aspose.Words for .NET?
R: Para reduzir o tamanho do documento PDF com amostragem de imagem usando Aspose.Words for .NET, siga estas etapas:

 Defina o caminho do diretório onde seus documentos estão localizados, substituindo`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do seu diretório de documentos.

 Carregue o documento que deseja converter para PDF usando o`Document` class e especifique o caminho para o documento no diretório de documentos especificado.

 Configure as opções de salvar como PDF criando uma instância do arquivo`PdfSaveOptions` classe e definir as opções de amostragem de imagem usando o`DownsampleOptions` propriedade. Você pode especificar a resolução desejada das imagens usando o`Resolution` propriedade e definir um limite mínimo de resolução acima do qual as imagens não serão reduzidas usando o`ResolutionThreshold` propriedade.

 Salve o documento em formato PDF usando o`Save` método do`Document` classe especificando o caminho e as opções de salvamento.

#### P: Quais são os benefícios de reduzir o tamanho do documento PDF com amostragem de imagens?
R: Os benefícios de reduzir o tamanho do documento PDF com amostragem de imagem são:

Tamanho reduzido do arquivo PDF: A amostragem de imagens reduz a resolução das imagens no documento PDF, resultando em uma diminuição significativa no tamanho do arquivo PDF. Isso facilita o compartilhamento e a transferência do arquivo, especialmente por e-mail ou online.

Otimização do espaço de armazenamento: Reduzir o tamanho do arquivo PDF ajuda a otimizar o uso do espaço de armazenamento, principalmente quando você possui muitos arquivos PDF contendo imagens em alta resolução.

Melhorias de desempenho: Arquivos PDF menores carregam mais rapidamente e podem ser abertos e visualizados mais rapidamente em diferentes dispositivos.