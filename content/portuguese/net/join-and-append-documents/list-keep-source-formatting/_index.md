---
title: Lista Manter Formatação Fonte
linktitle: Lista Manter Formatação Fonte
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como preservar a formatação da lista ao juntar e anexar documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/list-keep-source-formatting/
---

Este tutorial irá guiá-lo através do processo de uso do recurso List Keep Source Formatting do Aspose.Words for .NET. Este recurso permite juntar e anexar documentos do Word, preservando a formatação original das listas.

## Pré-requisitos

Antes de começar, certifique-se de ter o seguinte:

1. Aspose.Words para .NET instalado. Você pode baixá-lo do site Aspose ou instalá-lo via NuGet.
2. Visual Studio ou qualquer outro ambiente de desenvolvimento C#.

## Etapa 1: inicializar os diretórios de documentos

 Primeiro, você precisa definir o caminho para o diretório do seu documento. Modifique o valor do`dataDir` variável para o caminho onde seus documentos estão localizados.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Carregar os Documentos de Origem e Destino

Em seguida, você precisa carregar os documentos de origem e destino usando Aspose.Words.`Document` aula. Atualize os nomes dos arquivos no`Document` construtor de acordo com os nomes dos seus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Etapa 3: definir o documento de origem para fluir continuamente

 Para garantir que o conteúdo do documento de origem flua continuamente quando anexado ao documento de destino, você precisa definir a opção`SectionStart` propriedade da primeira seção no documento de origem para`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Etapa 4: anexar o documento de origem ao documento de destino

 Agora, você pode anexar o documento de origem ao documento de destino usando o`AppendDocument` método do`Document` aula. O`ImportFormatMode.KeepSourceFormatting` parâmetro garante que a formatação de origem, incluindo a formatação de listas, seja preservada durante a operação de acréscimo.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 5: salve o documento final

 Por fim, salve o documento mesclado com o recurso List Keep Source Formatting habilitado usando o`Save` método do`Document` aula.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Exemplo de código-fonte para formatação de origem de lista usando Aspose.Words para .NET 

Aqui está o código-fonte completo do recurso List Keep Source Formatting em C# usando Aspose.Words for .NET:

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Anexe o conteúdo do documento para que ele flua continuamente.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

É isso! Você implementou com sucesso o recurso List Keep Source Formatting usando Aspose.Words for .NET. O documento final conterá o conteúdo mesclado com a formatação de lista do documento de origem preservada.