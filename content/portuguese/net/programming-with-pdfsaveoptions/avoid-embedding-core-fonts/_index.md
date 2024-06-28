---
title: Reduza o tamanho do arquivo PDF não incorporando fontes principais
linktitle: Reduza o tamanho do arquivo PDF não incorporando fontes principais
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como reduzir o tamanho do arquivo PDF não incorporando fontes principais ao converter documentos do Word em PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

Neste tutorial, orientaremos você nas etapas de como reduzir o tamanho do arquivo PDF não incorporando fontes principais com Aspose.Words for .NET. Este recurso permite controlar se fontes básicas como Arial, Times New Roman, etc. devem ser incorporadas no PDF ao converter um documento do Word. Siga os passos abaixo:

## Passo 1: Carregando o documento

Comece enviando o documento do Word que deseja converter para PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Certifique-se de especificar o caminho correto para o seu documento do Word.

## Passo 2: Definir opções de conversão de PDF

Crie uma instância da classe PdfSaveOptions e ative a prevenção básica de incorporação de fontes:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Esta opção controla se as fontes básicas devem ser incorporadas no PDF ou não.

## Passo 3: Converter Documento em PDF

 Use o`Save` método para converter o documento Word em PDF especificando opções de conversão:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Certifique-se de especificar o caminho correto para salvar o PDF convertido.

### Exemplo de código-fonte para evitar a incorporação de fontes principais usando Aspose.Words for .NET

Aqui está o código-fonte completo para usar o recurso para evitar a incorporação de fontes principais com Aspose.Words for .NET:

```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// O PDF de saída não será incorporado com fontes básicas como Arial, Times New Roman etc.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Seguindo essas etapas, você pode controlar facilmente se as fontes básicas devem ser incorporadas no PDF ao converter um documento do Word com Aspose.Words for .NET.


## Conclusão

Neste tutorial, explicamos como reduzir o tamanho de um arquivo PDF não incorporando fontes básicas com Aspose.Words for .NET. Este recurso permite controlar se as fontes básicas devem ser incorporadas no PDF ao converter um documento do Word. Seguindo as etapas descritas, você pode controlar facilmente a incorporação ou não incorporação de fontes básicas, o que pode ajudar a reduzir o tamanho do arquivo PDF e garantir melhor compatibilidade e uma aparência consistente do documento em diferentes dispositivos e plataformas. Não se esqueça de considerar as consequências de não incorporar fontes básicas e de experimentar para garantir que o documento seja renderizado conforme o esperado.

### perguntas frequentes

#### P: Qual é a opção de não incorporar fontes básicas em um arquivo PDF e por que isso é importante?
R: A opção de não incorporar fontes básicas em um arquivo PDF controla se fontes básicas como Arial, Times New Roman, etc. devem ser incorporadas no PDF ao converter um documento do Word. Isso pode ser importante para reduzir o tamanho do arquivo PDF, evitando a inclusão de fontes comumente disponíveis em sistemas leitores de PDF. Também pode ajudar a garantir melhor compatibilidade e aparência consistente do documento PDF em diferentes dispositivos e plataformas.

#### P: Como posso configurar o Aspose.Words for .NET para não incorporar fontes básicas em um arquivo PDF?
R: Para configurar o Aspose.Words for .NET para não incorporar fontes principais em um arquivo PDF, siga estas etapas:

 Defina o caminho do diretório onde seus documentos estão localizados, substituindo`"YOUR DOCUMENTS DIRECTORY"` com o caminho real do seu diretório de documentos.

 Carregue o documento Word que deseja converter para PDF usando o`Document` classe e o caminho do documento especificado.

 Crie uma instância do`PdfSaveOptions` classe e definir o`UseCoreFonts`propriedade para`true`. Isso evitará a incorporação de fontes básicas no arquivo PDF gerado.

 Use o`Save` método do`Document` objeto para salvar o documento em formato PDF especificando as opções de conversão configuradas anteriormente.

#### P: Quais são os benefícios de não incorporar fontes básicas em um arquivo PDF?
R: Os benefícios de não incorporar fontes básicas em um arquivo PDF são:

Redução do tamanho do arquivo PDF: Ao evitar a incorporação de fontes comumente disponíveis, como Arial, Times New Roman, etc., o tamanho do arquivo PDF pode ser reduzido, facilitando o armazenamento, compartilhamento e transferência de arquivos.

Melhor compatibilidade: Ao usar fontes básicas comumente disponíveis em sistemas leitores de PDF, você garante melhor compatibilidade e aparência do documento em diferentes dispositivos e plataformas.

#### P: Quais são as consequências de não incorporar fontes básicas em um arquivo PDF?
R: As consequências de não incorporar fontes básicas em um arquivo PDF são as seguintes:

Aparência diferente: Caso as fontes base não estejam disponíveis no sistema onde o PDF é aberto, serão utilizadas fontes substitutas, o que pode resultar em uma aparência diferente da pretendida.

Problemas de legibilidade: As fontes substitutas usadas podem não ser tão legíveis quanto as fontes originais, o que pode afetar a legibilidade do documento.