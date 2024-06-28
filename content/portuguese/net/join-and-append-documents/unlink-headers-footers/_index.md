---
title: Desvincular cabeçalhos e rodapés
linktitle: Desvincular cabeçalhos e rodapés
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como juntar e anexar documentos do Word enquanto desvincula cabeçalhos e rodapés usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/unlink-headers-footers/
---

Este tutorial irá guiá-lo através do processo de uso do recurso Desvincular cabeçalhos e rodapés do Aspose.Words for .NET. Este recurso permite juntar e anexar documentos do Word enquanto desvincula cabeçalhos e rodapés do documento de origem.

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

## Etapa 3: desvincular cabeçalhos e rodapés do documento de origem

 Para desvincular os cabeçalhos e rodapés do documento de origem da continuação dos cabeçalhos e rodapés do documento de destino, você precisa definir a opção`LinkToPrevious` propriedade do`HeadersFooters` coleção na primeira seção do documento de origem para`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Etapa 4: anexar o documento de origem ao documento de destino

 Agora, você pode anexar o documento de origem ao documento de destino usando o`AppendDocument` método do`Document` aula. O`ImportFormatMode.KeepSourceFormatting` O parâmetro garante que a formatação de origem seja preservada durante a operação de acréscimo.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 5: salve o documento final

 Por fim, salve o documento mesclado com o recurso Desvincular cabeçalhos e rodapés habilitado usando o`Save` método do`Document` aula.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Exemplo de código-fonte para desvincular cabeçalhos e rodapés usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso "Desvincular cabeçalhos e rodapés" em C# usando Aspose.Words for .NET:

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Desvincule os cabeçalhos e rodapés do documento de origem para impedir isso
	// de continuar os cabeçalhos e rodapés do documento de destino.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

É isso! Você implementou com sucesso o recurso Desvincular cabeçalhos e rodapés usando Aspose.Words for .NET. O documento final conterá o conteúdo mesclado com os cabeçalhos e rodapés do documento de origem desvinculados do documento de destino.