---
title: Comportamento de estilo inteligente
linktitle: Comportamento de estilo inteligente
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como manter um comportamento de estilo inteligente ao juntar e anexar documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/smart-style-behavior/
---

Este tutorial irá guiá-lo através do processo de uso do recurso Smart Style Behavior do Aspose.Words for .NET. Este recurso permite juntar e anexar documentos do Word enquanto mantém um comportamento de estilo inteligente.

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

## Etapa 3: insira uma quebra de página no documento de destino

 Para garantir que o conteúdo anexado apareça em uma nova página do documento de destino, você pode inserir uma quebra de página usando um`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Etapa 4: definir opções de comportamento de estilo inteligente

Para ativar o comportamento de estilo inteligente durante a operação de acréscimo, você precisa criar uma instância de`ImportFormatOptions` e definir o`SmartStyleBehavior`propriedade para`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Etapa 5: anexar o documento de origem ao documento de destino

 Agora, você pode anexar o documento de origem ao documento de destino usando o`InsertDocument` método do`DocumentBuilder` aula. Use o`ImportFormatMode.UseDestinationStyles` parâmetro e passe o`ImportFormatOptions` objeto para manter o comportamento de estilo inteligente.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Etapa 6: salve o documento final

 Por fim, salve o documento mesclado com o recurso Smart Style Behavior habilitado usando o`Save` método do`Document` aula.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Exemplo de código-fonte para Smart Style Behavior usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso "Smart Style Behavior" em C# usando Aspose.Words for .NET:
 
```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

É isso! Você implementou com sucesso o recurso Smart Style Behavior usando Aspose.Words for .NET. O documento final conterá o conteúdo mesclado com o comportamento de estilo inteligente mantido.