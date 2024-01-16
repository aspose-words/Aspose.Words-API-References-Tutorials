---
title: Otimize o tamanho do PDF com fontes Skip Embedded Arial e Times Roman
linktitle: Otimize o tamanho do PDF com fontes Skip Embedded Arial e Times Roman
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para gerar PDF otimizado sem incorporar fontes Arial e Times Roman com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Este artigo fornece um guia passo a passo sobre como usar o recurso para otimizar o tamanho do PDF, ignorando as fontes Arial e Times Roman incorporadas para o tamanho do metarquivo com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial você poderá entender como configurar a opção de modo de incorporação de fontes em um documento e gerar um PDF sem incorporar fontes Arial e Times Roman.

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

## Etapa 3: configurar opções de salvar como PDF com incorporação de fonte

 Para ignorar a incorporação de fontes Arial e Times Roman no PDF gerado, precisamos configurar o`PdfSaveOptions` objeto e definir o`FontEmbeddingMode`propriedade para`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Passo 4: Salve o documento como PDF sem fontes incorporadas

Por fim, podemos salvar o documento em formato PDF utilizando as opções de salvamento configuradas anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Isso é tudo ! Você gerou com sucesso um PDF sem incorporar fontes Arial e Times Roman usando Aspose.Words for .NET.

### Exemplo de código-fonte para ignorar fontes Arial e Times Roman incorporadas no tamanho do metarquivo com Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Conclusão

Neste tutorial, explicamos como desabilitar a incorporação de fontes Arial e Times Roman em um documento PDF usando Aspose.Words for .NET. Seguindo as etapas descritas, você pode gerar um arquivo PDF sem incorporar essas fontes específicas, o que pode ajudar a reduzir o tamanho do arquivo e garantir melhor compatibilidade de documentos em diferentes plataformas. Certifique-se de considerar as consequências de desativar a incorporação de fontes ao usar esse recurso. Sinta-se à vontade para explorar mais recursos do Aspose.Words for .NET para otimizar a geração de seus arquivos PDF.

### perguntas frequentes

#### P: O que é desativar a incorporação de fontes Arial e Times Roman em um documento PDF e por que isso é importante?
R: Desabilitar a incorporação de fontes Arial e Times Roman em um documento PDF é o processo de não incluir essas fontes no arquivo PDF gerado. Isso pode ser importante para reduzir o tamanho do arquivo PDF, evitando a inclusão de fontes que já estão comumente disponíveis em sistemas leitores de PDF. Também pode ajudar a garantir melhor compatibilidade e aparência consistente do documento PDF em diferentes dispositivos e plataformas.

#### P: Como posso configurar o Aspose.Words for .NET para não incorporar fontes Arial e Times Roman em um documento PDF?
R: Para configurar o Aspose.Words for .NET para não incorporar fontes Arial e Times Roman em um documento PDF, siga estas etapas:

 Defina o caminho do diretório onde seus documentos estão localizados, substituindo`"YOUR DOCUMENT DIRECTORY"` com o caminho real do seu diretório de documentos.

 Carregue o documento que deseja processar usando o`Document` classe e o caminho do documento especificado.

 Crie uma instância do`PdfSaveOptions` classe e definir o`FontEmbeddingMode`propriedade para`PdfFontEmbeddingMode.EmbedAll`. Isto irá incorporar todas as fontes, exceto Arial e Times Roman, no arquivo PDF gerado.

 Use o`Save` método do`Document` objeto para salvar o documento em formato PDF especificando as opções de salvamento configuradas anteriormente.

#### P: Quais são os benefícios de desativar a incorporação de fontes Arial e Times Roman em um documento PDF?
R: Os benefícios de desativar a incorporação de fontes Arial e Times Roman em um documento PDF são:

Redução do tamanho do arquivo PDF: Ao evitar a incorporação de fontes comumente disponíveis, como Arial e Times Roman, o tamanho do arquivo PDF pode ser reduzido, facilitando o armazenamento, o compartilhamento e a transferência de arquivos.

Melhor compatibilidade: Ao usar fontes comumente disponíveis em sistemas leitores de PDF, você garante melhor compatibilidade e aparência do documento em diferentes dispositivos e plataformas.

#### P: Quais são as consequências de desativar a incorporação de fontes Arial e Times Roman em um documento PDF?
R: As consequências de desabilitar a incorporação de fontes Arial e Times Roman em um documento PDF são as seguintes:

Aparência diferente: Se as fontes Arial e Times Roman não estiverem disponíveis no sistema onde o PDF é aberto, serão utilizadas fontes substitutas, o que pode resultar em uma aparência diferente da pretendida.

Problemas de legibilidade: As fontes substitutas usadas podem não ser tão legíveis quanto as fontes originais, o que pode afetar a legibilidade do documento.