---
title: Reinicie a numeração de páginas
linktitle: Reinicie a numeração de páginas
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como reiniciar a numeração de páginas ao juntar e anexar documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/restart-page-numbering/
---

Este tutorial irá guiá-lo através do processo de uso do recurso Reiniciar numeração de página do Aspose.Words for .NET. Este recurso permite unir e anexar documentos do Word enquanto reinicia a numeração de páginas no documento de origem.

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

## Etapa 3: definir o documento de origem para reiniciar a numeração de páginas

 Para reiniciar a numeração de páginas no documento de origem, você precisa definir o`SectionStart` propriedade da primeira seção no documento de origem para`SectionStart.NewPage` e definir o`RestartPageNumbering`propriedade para`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Etapa 4: anexar o documento de origem ao documento de destino

 Agora, você pode anexar o documento de origem ao documento de destino usando o`AppendDocument` método do`Document` aula. O`ImportFormatMode.KeepSourceFormatting` O parâmetro garante que a formatação de origem seja preservada durante a operação de acréscimo.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 5: salve o documento final

 Por fim, salve o documento mesclado com o recurso Reiniciar numeração de página habilitado usando o`Save` método do`Document` aula.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Exemplo de código-fonte para reiniciar numeração de página usando Aspose.Words for .NET

Aqui está o código-fonte completo para o recurso "Reiniciar numeração de páginas" em C# usando Aspose.Words for .NET:
 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

É isso! Você implementou com sucesso o recurso Reiniciar numeração de página usando Aspose.Words for .NET. O documento final conterá o conteúdo mesclado com a numeração de páginas reiniciada no documento de origem.