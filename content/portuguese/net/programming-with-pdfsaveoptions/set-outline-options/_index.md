---
title: Definir opções de estrutura de tópicos em um documento PDF
linktitle: Definir opções de estrutura de tópicos em um documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para definir opções de estrutura de tópicos em um documento PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/set-outline-options/
---

Este artigo fornece um guia passo a passo sobre como usar o recurso definir opções de estrutura de tópicos para tamanho de metarquivo com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial, você poderá entender como definir opções de estrutura de tópicos em um documento e gerar um PDF com as opções de estrutura de tópicos correspondentes.

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

## Etapa 3: configurar opções de salvar como PDF com opções de plano

 Para definir opções de contorno no PDF gerado, precisamos configurar o`PdfSaveOptions` objeto. Podemos definir o número de níveis de contorno do título (`HeadingsOutlineLevels`) e o número de níveis de estrutura de tópicos expandidos (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Passo 4: Salve o documento como PDF com opções de estrutura de tópicos

Por fim, podemos salvar o documento em formato PDF utilizando as opções de salvamento configuradas anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Isso é tudo ! Você definiu com êxito as opções de estrutura de tópicos em um documento e gerou um PDF com as opções de estrutura de tópicos correspondentes usando Aspose.Words for .NET.

### Exemplo de código-fonte para definir opções de plano para tamanho de metarquivo com Aspose.Words for .NET


```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Conclusão

Neste tutorial, explicamos como definir opções de estrutura de tópicos em um documento PDF usando Aspose.Words for .NET. Usando as etapas descritas, você pode especificar facilmente os níveis de título e estrutura de tópicos em seu documento e gerar um arquivo PDF com as opções de estrutura de tópicos correspondentes. Aproveite os benefícios da opção de estrutura de tópicos para melhorar a estrutura e a navegação em seus documentos PDF usando Aspose.Words for .NET.

### perguntas frequentes

#### P: Qual é a opção de estrutura de tópicos em um documento PDF?
R: A opção de estrutura de tópicos em um documento PDF refere-se à estrutura hierárquica do conteúdo do documento. Permite criar um índice interativo e facilita a navegação no documento. As opções de estrutura de tópicos determinam os níveis de título e subtítulo a serem incluídos na estrutura de tópicos e o nível de detalhe a ser exibido na estrutura de tópicos gerada.

#### P: Como posso definir opções de estrutura de tópicos em um documento PDF usando Aspose.Words for .NET?
R: Para definir opções de estrutura de tópicos em um documento PDF usando Aspose.Words for .NET, siga estas etapas:

 Defina o caminho do diretório onde seus documentos estão localizados, substituindo`"YOUR DOCUMENT DIRECTORY"` com o caminho real do seu diretório de documentos.

 Carregue o documento que deseja converter para PDF usando o`Document` class e especifique o caminho para o documento no diretório de documentos especificado.

 Configure as opções de salvar como PDF criando uma instância do arquivo`PdfSaveOptions` classe e usando o`OutlineOptions` propriedade para definir as opções de estrutura de tópicos. Você pode especificar o número de níveis de título a serem incluídos no esboço usando o botão`HeadingsOutlineLevels` propriedade e o número de níveis de estrutura de tópicos expandidos usando a propriedade`ExpandedOutlineLevels` propriedade.

 Salve o documento em formato PDF usando o`Save` método do`Document` classe especificando o caminho e as opções de salvamento.

#### P: Qual é a opção de plano em um documento PDF?
R: A opção de estrutura de tópicos em um documento PDF permite criar uma estrutura hierárquica do conteúdo, o que facilita a navegação no documento e o acesso às diferentes seções. Isso permite que os usuários pulem rapidamente para partes específicas do documento clicando nas entradas do índice ou do esboço. A opção de estrutura de tópicos também aprimora a experiência de leitura, fornecendo uma visão geral da estrutura geral do documento.
