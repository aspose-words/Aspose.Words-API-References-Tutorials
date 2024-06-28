---
title: Cabeçalhos de links e rodapés
linktitle: Cabeçalhos de links e rodapés
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como vincular cabeçalhos e rodapés ao juntar e anexar documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/link-headers-footers/
---

Este tutorial irá guiá-lo através do processo de uso do recurso Link Headers Footers do Aspose.Words for .NET. Este recurso permite unir e anexar vários documentos do Word enquanto vincula os cabeçalhos e rodapés do documento de origem à seção anterior do documento de destino.

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Etapa 3: definir o documento anexado para aparecer em uma nova página

 Para garantir que o conteúdo do documento de origem apareça em uma nova página do documento de destino, você precisa definir a opção`SectionStart` propriedade da primeira seção no documento de origem para`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Etapa 4: vincular cabeçalhos e rodapés à seção anterior

 Para vincular os cabeçalhos e rodapés do documento de origem à seção anterior do documento de destino, você pode usar o comando`LinkToPrevious` método do`HeadersFooters` coleção. Ao passar`true` como parâmetro, você substitui quaisquer cabeçalhos ou rodapés existentes no documento de origem.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Etapa 5: anexar o documento de origem ao documento de destino

 Agora, você pode anexar o documento de origem ao documento de destino usando o`AppendDocument` método do`Document` aula. O`ImportFormatMode.KeepSourceFormatting` O parâmetro garante que a formatação de origem seja preservada durante a operação de acréscimo.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 6: salve o documento final

 Por fim, salve o documento mesclado com os cabeçalhos e rodapés vinculados usando o`Save` método do`Document` aula.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Exemplo de código-fonte para cabeçalhos de links e rodapés usando Aspose.Words para .NET 

Aqui está o código-fonte completo do recurso "Link Headers Footers" em C# usando Aspose.Words for .NET:


```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Defina o documento anexado para aparecer em uma nova página.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Vincule os cabeçalhos e rodapés do documento de origem à seção anterior.
	// Isto substituirá quaisquer cabeçalhos ou rodapés já encontrados no documento de origem.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

É isso! Você implementou com sucesso o recurso Link Headers Footers usando Aspose.Words for .NET. O documento final conterá o conteúdo mesclado com os cabeçalhos e rodapés do documento de origem vinculado à seção anterior do documento de destino.