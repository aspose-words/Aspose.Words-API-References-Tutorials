---
title: Atualizar a última propriedade impressa no documento PDF
linktitle: Atualizar a última propriedade impressa no documento PDF
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para atualizar a propriedade "Última impressão" ao converter para PDF com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Este artigo fornece um guia passo a passo sobre como usar a propriedade "Última impressão" no recurso de atualização de documentos PDF com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial você poderá entender como configurar a opção de atualização da propriedade “Última impressão” na conversão para PDF.

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

## Etapa 3: configurar as opções de salvar como PDF com a propriedade "Última impressão" atualizada

 Para habilitar a atualização da propriedade "Última Impresso" ao converter para PDF, precisamos configurar o`PdfSaveOptions` objeto e definir o`UpdateLastPrintedProperty`propriedade para`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Passo 4: Salve o documento como PDF com a atualização da propriedade “Última impressão”

Por fim, podemos salvar o documento em formato PDF utilizando as opções de salvamento configuradas anteriormente.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Isso é tudo ! Você ativou com sucesso a atualização da propriedade "Última impressão" ao converter um documento em PDF usando Aspose.Words for .NET.

### Exemplo de código-fonte para atualização da propriedade "Última impressão" com Aspose.Words para .NET


```csharp

	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Conclusão

Neste tutorial, explicamos como atualizar a propriedade “Última impressão” em um documento PDF usando Aspose.Words for .NET. Seguindo os passos indicados, você pode configurar facilmente a opção de atualização da propriedade “Última impressão” ao converter um documento para PDF. Use esse recurso para acompanhar o uso de documentos e informações relacionadas.

### perguntas frequentes

#### P: Qual é a propriedade "Última impressão" em um documento PDF?
R: A propriedade "Última impressão" em um documento PDF refere-se à data e hora em que o documento foi impresso pela última vez. Esta propriedade pode ser útil para rastrear informações sobre uso e gerenciamento de documentos.

#### P: Como posso atualizar a propriedade “Última impressão” em um documento PDF com Aspose.Words for .NET?
R: Para atualizar a propriedade "Última impressão" em um documento PDF com Aspose.Words for .NET, siga estas etapas:

 Crie uma instância do`Document` classe especificando o caminho para o documento do Word.

 Crie uma instância do`PdfSaveOptions` classe e definir o`UpdateLastPrintedProperty`propriedade para`true` para ativar a atualização da propriedade "Última impressão".

 Use o`Save` método do`Document`class para salvar o documento em formato PDF especificando opções de salvamento.

#### P: Como posso verificar se a propriedade “Última Impressão” foi atualizada no documento PDF gerado?
R: Você pode verificar se a propriedade "Última impressão" foi atualizada no documento PDF gerado abrindo o arquivo PDF com um visualizador de PDF compatível, como o Adobe Acrobat Reader, e visualizando as informações do documento. A data e hora da última impressão deverão corresponder à data e hora de geração do documento PDF.
