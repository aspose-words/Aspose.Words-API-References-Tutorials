---
title: Remover rodapés de cabeçalhos de origem
linktitle: Remover rodapés de cabeçalhos de origem
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como remover cabeçalhos e rodapés ao juntar e anexar documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/remove-source-headers-footers/
---

Este tutorial irá guiá-lo através do processo de uso do recurso Remover cabeçalhos de origem e rodapés do Aspose.Words for .NET. Este recurso permite juntar e anexar documentos do Word enquanto remove cabeçalhos e rodapés do documento de origem.

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

## Etapa 3: remover cabeçalhos e rodapés das seções do documento de origem

 Para remover os cabeçalhos e rodapés de cada seção do documento de origem, você pode percorrer as seções usando um`foreach` faça um loop e chame o`ClearHeadersFooters` método.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Etapa 4: desative a configuração "LinkToPrevious" para HeadersFooters

Mesmo depois de limpar os cabeçalhos e rodapés do documento de origem, existe a possibilidade de que a configuração "LinkToPrevious" para`HeadersFooters` ainda pode ser definido. Para evitar esse comportamento, você precisa defini-lo explicitamente como`false` para a primeira seção`HeadersFooters` propriedade.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Etapa 5: anexar o documento de origem ao documento de destino

 Agora, você pode anexar o documento de origem ao documento de destino usando o`AppendDocument` método do`Document` aula. O`ImportFormatMode.KeepSourceFormatting` O parâmetro garante que a formatação de origem seja preservada durante a operação de acréscimo.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 6: salve o documento final

 Por fim, salve o documento mesclado com o recurso Remover cabeçalhos de origem e rodapés habilitado usando o`Save` método do`Document` aula.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Exemplo de código-fonte para remover rodapés de cabeçalhos de origem usando Aspose.Words for .NET 

Aqui está o código-fonte completo do recurso "Remover rodapés de cabeçalhos de origem" em C# usando Aspose.Words for .NET:


```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Remova os cabeçalhos e rodapés de cada uma das seções do documento de origem.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Mesmo depois que os cabeçalhos e rodapés forem apagados do documento de origem, a configuração "LinkToPrevious"
	// para HeadersFooters ainda pode ser definido. Isso fará com que os cabeçalhos e rodapés continuem a partir do destino
	// documento. Isso deve ser definido como falso para evitar esse comportamento.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
É isso! Você implementou com êxito o recurso Remover cabeçalhos de origem e rodapés usando Aspose.Words for .NET. O documento final conterá o conteúdo mesclado com os cabeçalhos e rodapés removidos do documento de origem.