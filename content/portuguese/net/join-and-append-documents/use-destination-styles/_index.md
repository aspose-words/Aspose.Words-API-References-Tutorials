---
title: Use estilos de destino
linktitle: Use estilos de destino
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como unir e anexar documentos do Word ao aplicar estilos de documentos de destino usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/use-destination-styles/
---

Este tutorial irá guiá-lo através do processo de uso do recurso Usar estilos de destino do Aspose.Words for .NET. Este recurso permite unir e anexar documentos do Word enquanto aplica os estilos do documento de destino.

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

Em seguida, você precisa carregar os documentos de origem e destino usando o Aspose.Words`Document` aula. Atualize os nomes dos arquivos no`Document` construtor de acordo com os nomes dos seus documentos.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Etapa 3: anexar o documento de origem aos estilos de destino

 Para anexar o documento de origem ao documento de destino enquanto aplica os estilos do documento de destino, você pode usar o`AppendDocument` método do`Document` aula com o`ImportFormatMode.UseDestinationStyles` parâmetro.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Etapa 4: salve o documento final

 Por fim, salve o documento mesclado com o recurso Usar estilos de destino habilitado usando o`Save` método do`Document` aula.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Exemplo de código-fonte para usar estilos de destino usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso "Usar estilos de destino" em C# usando Aspose.Words for .NET:

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Anexe o documento de origem usando os estilos do documento de destino.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

É isso! Você implementou com sucesso o recurso Usar estilos de destino usando Aspose.Words for .NET. O documento final conterá o conteúdo mesclado com os estilos do documento de destino aplicados.