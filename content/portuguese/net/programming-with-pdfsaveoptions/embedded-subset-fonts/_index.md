---
title: Incorporar fontes de subconjunto em documento PDF
linktitle: Incorporar fontes de subconjunto em documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para incorporar subconjuntos de fontes em um documento PDF usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Este artigo fornece um guia passo a passo sobre como usar o recurso de incorporação de subconjunto de fontes com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial, você poderá entender como incorporar subconjuntos de fontes em um documento e gerar um PDF contendo apenas os glifos utilizados no documento.

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

## Etapa 3: configurar as opções de salvar como PDF

 Para criar um PDF contendo apenas os subconjuntos de fontes utilizadas no documento, precisamos configurar o`PdfSaveOptions` objeto com o`EmbedFullFonts` propriedade definida como`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Etapa 4: salve o documento como PDF com subconjuntos de fontes

 Finalmente, podemos salvar o documento como PDF usando os subconjuntos de fontes. Especifique o nome do arquivo de saída e o`saveOptions` objeto que configuramos na etapa anterior.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Isso é tudo ! Você incorporou com sucesso subconjuntos de fontes em um documento e gerou um PDF contendo apenas os glifos usados no documento com Aspose.Words for .NET.

### Exemplo de código-fonte para incorporar subconjuntos de fontes com Aspose.Words for .NET

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// O PDF de saída conterá subconjuntos das fontes do documento.
	// Somente os glifos usados no documento são incluídos nas fontes do PDF.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Conclusão

Neste tutorial, aprendemos como incorporar subconjuntos de fontes em um documento PDF usando Aspose.Words for .NET. A incorporação de subconjuntos de fontes ajuda a reduzir o tamanho do arquivo PDF enquanto preserva a aparência do documento usando apenas os caracteres realmente usados. Isso garante melhor compatibilidade e desempenho ao visualizar e imprimir o PDF. Sinta-se à vontade para explorar ainda mais os recursos do Aspose.Words for .NET para otimizar a geração de seus documentos PDF com subconjuntos de fontes incorporados.

### perguntas frequentes

#### P: O que é incorporar subconjuntos de fontes em um documento PDF?
R: Incorporar subconjuntos de fontes em um documento PDF é o processo de incluir apenas os glifos usados no documento, em vez de incluir todas as fontes completas. Isso reduz o tamanho do arquivo PDF, incluindo apenas os dados de fonte necessários para exibir os caracteres realmente usados no documento.

#### P: Qual é a diferença entre incorporar fontes completas e incorporar subconjuntos de fontes?
R: Incorporação completa de fontes significa incluir todas as fontes usadas no documento no arquivo PDF, o que garante que o documento será exibido exatamente como foi projetado, mas pode aumentar o tamanho do arquivo PDF. Por outro lado, a incorporação de subconjuntos de fontes contém apenas os glifos usados no documento, reduzindo assim o tamanho do arquivo PDF, mas limitando a capacidade de replicar exatamente a aparência do documento se caracteres adicionais forem adicionados posteriormente.

#### P: Como posso incorporar subconjuntos de fontes em um documento PDF usando Aspose.Words for .NET?
R: Para incorporar subconjuntos de fontes em um documento PDF usando Aspose.Words for .NET, siga estas etapas:

 Defina o caminho do diretório do documento substituindo`"YOUR DOCUMENT DIRECTORY"` com o caminho real do seu diretório de documentos.

 Carregue o documento que deseja processar usando o`Document` classe e o caminho do documento.

 Configure as opções de salvamento de PDF criando uma instância do arquivo`PdfSaveOptions` classe e definir o`EmbedFullFonts`propriedade para`false`Isso garante que apenas os subconjuntos de fontes usados no documento serão incluídos no arquivo PDF.

 Salve o documento em formato PDF com os subconjuntos de fontes incorporados usando o`Save` método do`Document` objeto, especificando o nome do arquivo de saída e as opções de salvamento configuradas anteriormente.

#### P: Quais são os benefícios de incorporar subconjuntos de fontes em um documento PDF?
R: Os benefícios de incorporar subconjuntos de fontes em um documento PDF são:

Tamanho reduzido do arquivo PDF: Ao incluir apenas os glifos usados no documento, o tamanho do arquivo PDF é reduzido em comparação com a incorporação de fontes completas.

Preservação da aparência do documento: Os subconjuntos de fontes incluídos no arquivo PDF permitem reproduzir a aparência do documento utilizando apenas os caracteres efetivamente utilizados.

Compatibilidade com as restrições da Licença: A incorporação de subconjuntos de fontes pode ser preferida nos casos em que as fontes completas não podem ser incorporadas legalmente devido a restrições de licenciamento.