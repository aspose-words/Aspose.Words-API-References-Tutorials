---
title: Incorporar fontes em documentos PDF
linktitle: Incorporar fontes em documentos PDF
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para incorporar fontes em um PDF usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

Este artigo fornece um guia passo a passo sobre como usar o recurso incorporar fontes em documentos PDF do Aspose.Words for .NET. Percorreremos o trecho de código e explicaremos cada parte em detalhes. Ao final deste tutorial, você será capaz de entender como incorporar todas as fontes em um documento e gerar um PDF com as fontes incorporadas usando Aspose.Words for .NET.

Antes de começarmos, certifique-se de ter a biblioteca Aspose.Words for .NET instalada e configurada em seu projeto. Você pode encontrar a biblioteca e as instruções de instalação no site do Aspose.

## Etapa 1: definir o caminho do diretório do documento

 Para começar, você precisa definir o caminho para o diretório onde seus documentos estão localizados. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passo 2: Carregue o documento

A seguir, precisamos carregar o documento que queremos processar. Neste exemplo, presumimos que o documento se chama "Rendering.docx" e está localizado no diretório de documentos especificado.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Passo 3: Configure as opções de salvamento do PDF

 Para incorporar todas as fontes no PDF resultante, precisamos configurar o`PdfSaveOptions` objeto com o`EmbedFullFonts` propriedade definida como`true`. Isso garante que todas as fontes usadas no documento sejam incluídas no arquivo PDF gerado.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## Passo 4: Salve o documento como PDF com fontes incorporadas

 Finalmente, podemos salvar o documento como um arquivo PDF com as fontes incorporadas. Especifique o nome do arquivo de saída e o`saveOptions` objeto que configuramos na etapa anterior.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

É isso! Você incorporou com sucesso todas as fontes em um documento e gerou um PDF com as fontes incorporadas usando Aspose.Words for .NET.

### Exemplo de código-fonte para todas as fontes incorporadas usando Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// O PDF de saída será incorporado com todas as fontes encontradas no documento.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## Conclusão

Neste tutorial, aprendemos como incorporar todas as fontes em um documento PDF usando Aspose.Words for .NET. A incorporação de fontes garante que as fontes especificadas no documento estarão disponíveis e serão exibidas corretamente, mesmo que não estejam instaladas no sistema onde o PDF é aberto. Isso garante uma aparência consistente e uma formatação precisa de documentos em diferentes dispositivos e plataformas. Sinta-se à vontade para explorar mais recursos do Aspose.Words for .NET para otimizar a geração de seus documentos PDF com fontes incorporadas.

### perguntas frequentes

#### P: O que é incorporar fontes em um documento PDF e por que isso é importante?
R: Incorporar fontes em um documento PDF é o processo de incluir todas as fontes usadas no documento no próprio arquivo PDF. Isso garante que as fontes especificadas no documento estarão disponíveis e serão exibidas corretamente, mesmo que as fontes não estejam instaladas no sistema onde o PDF é aberto. A incorporação de fontes é importante para preservar a aparência e a formatação do documento, garantindo que as fontes sejam renderizadas de forma consistente em diferentes dispositivos e plataformas.

#### P: Como posso incorporar todas as fontes em um documento PDF usando Aspose.Words for .NET?
R: Para incorporar todas as fontes em um documento PDF usando Aspose.Words for .NET, siga estas etapas:

 Defina o caminho do diretório do documento substituindo`"YOUR DOCUMENT DIRECTORY"` com o caminho real do seu diretório de documentos.

 Carregue o documento que deseja processar usando o`Document` classe e o caminho do documento.

 Configure as opções de salvamento de PDF criando uma instância do arquivo`PdfSaveOptions` classe e definir o`EmbedFullFonts`propriedade para`true`. Isso garante que todas as fontes utilizadas no documento serão incorporadas no arquivo PDF gerado.

 Salve o documento em formato PDF com fontes incorporadas usando o`Save` método do`Document`objeto, especificando o nome do arquivo de saída e as opções de salvamento configuradas anteriormente.

#### P: Por que é importante incorporar todas as fontes em um documento PDF?
R: Incorporar todas as fontes em um documento PDF é importante para garantir que o documento será exibido corretamente, mesmo que as fontes especificadas não estejam disponíveis no sistema onde o PDF é aberto. Isso ajuda a preservar a aparência, a formatação e a legibilidade do documento, garantindo que as fontes usadas sejam renderizadas de forma consistente em diferentes dispositivos e plataformas.

#### P: Quais são os benefícios de incorporar fontes em um documento PDF?
R: Os benefícios de incorporar fontes em um documento PDF são:

Garanta uma aparência consistente do documento: As fontes incorporadas garantem que o documento será exibido exatamente como foi projetado, independentemente das fontes disponíveis no sistema.

Preservação da formatação: as fontes incorporadas preservam a formatação e o layout do documento, evitando substituições de fontes e variações na aparência.

Legibilidade aprimorada: A incorporação de fontes garante melhor legibilidade do documento, pois as fontes especificadas são usadas para exibir o texto, mesmo que as fontes originais não estejam disponíveis.

#### P: A incorporação de todas as fontes aumenta o tamanho do arquivo PDF?
R: Sim, incorporar todas as fontes em um documento PDF pode aumentar o tamanho do arquivo PDF gerado, pois os dados da fonte devem ser incluídos no arquivo. No entanto, este aumento no tamanho é geralmente insignificante para a maioria dos documentos, e os benefícios da incorporação de fontes muitas vezes superam este ligeiro aumento no tamanho.

#### P: Posso selecionar fontes específicas para incorporar em um documento PDF?
 R: Sim, com Aspose.Words for .NET você pode selecionar fontes específicas para incorporar em um documento PDF usando opções de configuração avançadas. Por exemplo, você pode usar o`SubsetFonts` propriedade do`PdfSaveOptions` objeto para especificar quais fontes incluir ou usar opções adicionais para definir filtros de seleção de fontes personalizados.