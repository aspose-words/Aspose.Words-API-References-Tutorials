---
title: Reduza o tamanho do PDF desativando fontes incorporadas
linktitle: Reduza o tamanho do PDF desativando fontes incorporadas
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como reduzir o tamanho do PDF desabilitando a incorporação de fontes do Windows ao converter documentos em PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

Neste tutorial, orientaremos você nas etapas para reduzir o tamanho do PDF desabilitando a incorporação de fontes do Windows em um documento PDF com Aspose.Words for .NET. Ao desativar a incorporação de fontes, você pode reduzir o tamanho do arquivo PDF gerado. Siga os passos abaixo:

## Passo 1: Carregando o documento

Comece enviando o documento que deseja converter para PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Certifique-se de especificar o caminho correto para o seu documento.

## Passo 2: Definir opções para salvar PDF

Crie uma instância da classe PdfSaveOptions e especifique como incorporar fontes:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Esta opção permite desativar a integração de fontes do Windows no arquivo PDF gerado.

## Passo 3: Converter Documento em PDF

 Use o`Save` método para converter o documento em PDF especificando opções de conversão:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Certifique-se de especificar o caminho correto para salvar o PDF convertido.

### Exemplo de código-fonte para desativar fontes incorporadas do Windows usando Aspose.Words for .NET

Aqui está o código-fonte completo para desativar a incorporação de fontes do Windows em um documento PDF com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// O PDF de saída será salvo sem incorporar fontes padrão do Windows.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Seguindo essas etapas, você pode facilmente desabilitar a incorporação de fontes do Windows em um documento PDF com Aspose.Words for .NET.


## Conclusão

Neste tutorial, aprendemos como reduzir o tamanho de um arquivo PDF desativando a incorporação de fontes do Windows usando Aspose.Words for .NET. Ao desativar a incorporação de fontes, você pode reduzir o tamanho do arquivo PDF gerado, facilitando o armazenamento, o compartilhamento e a transferência de arquivos. No entanto, é importante observar que desabilitar a incorporação de fontes do Windows pode causar alterações na aparência e na formatação do documento PDF final. Certifique-se de considerar essas consequências ao usar esse recurso. Sinta-se à vontade para explorar mais recursos do Aspose.Words for .NET para otimizar a geração de seus arquivos PDF.

### perguntas frequentes

#### P: O que é desabilitar a incorporação de fontes do Windows em um documento PDF e por que isso é importante?
R: Desabilitar a incorporação de fontes do Windows em um documento PDF é o processo que evita que fontes do Windows sejam incluídas no arquivo PDF gerado. Isso reduz o tamanho do arquivo PDF removendo dados de fontes incorporados do Windows. Isso pode ser importante para reduzir o tamanho dos arquivos PDF, o que pode torná-los mais fáceis de armazenar, compartilhar e transferir com mais rapidez.

#### P: Como posso desativar a incorporação de fontes do Windows em um documento PDF usando Aspose.Words for .NET?
R: Para desativar a incorporação de fontes do Windows em um documento PDF usando Aspose.Words for .NET, siga estas etapas:

 Carregue o documento que deseja converter para PDF usando o`Document` classe e caminho do documento.

 Crie uma instância do`PdfSaveOptions` classe e definir o`FontEmbeddingMode`propriedade para`PdfFontEmbeddingMode.EmbedNone`. Isso desativa a incorporação de fontes do Windows no arquivo PDF gerado.

 Use o`Save` método do`Document` objeto para converter o documento em PDF especificando as opções de conversão configuradas anteriormente.

#### P: Quais são os benefícios de desativar a incorporação de fontes do Windows em um documento PDF?
R: Os benefícios de desabilitar a incorporação de fontes do Windows em um documento PDF são:

Tamanho reduzido do arquivo PDF: Ao desativar a incorporação de fontes do Windows, os dados de fontes incorporadas do Windows são removidos, reduzindo o tamanho do arquivo PDF gerado.

Armazenamento mais fácil: Arquivos PDF menores são mais fáceis de armazenar, salvar e transferir.

Compartilhamento e transferência mais rápidos: Arquivos PDF menores podem ser compartilhados e transferidos mais rapidamente, economizando tempo e recursos.

#### P: Quais são as consequências de desativar a incorporação de fontes do Windows em um documento PDF?
R: Desabilitar a incorporação de fontes do Windows em um documento PDF pode levar a consequências como:

Perda de aparência e formatação: Se as fontes do Windows especificadas no documento não estiverem disponíveis no sistema onde o PDF é aberto, serão utilizadas fontes substitutas, o que pode resultar em aparência e formatação incorretas. formato diferente do esperado.

Problemas de legibilidade: Se as fontes substitutas usadas não forem tão legíveis quanto as fontes originais, isso poderá afetar a legibilidade do texto no documento PDF.