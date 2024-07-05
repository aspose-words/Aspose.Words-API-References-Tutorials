---
title: Mantenha a fonte unida
linktitle: Mantenha a fonte unida
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar Aspose.Words for .NET para unir e anexar documentos do Word enquanto mantém o conteúdo de origem junto com o documento de destino.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/keep-source-together/
---

Este tutorial irá guiá-lo através do processo de uso do recurso Keep Source Together do Aspose.Words for .NET. Este recurso permite unir e anexar vários documentos do Word, mantendo o conteúdo do documento de origem junto com o conteúdo do documento de destino. 

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Etapa 3: definir o documento de origem para aparecer após o conteúdo do documento de destino

 Para garantir que o documento de origem apareça imediatamente após o conteúdo do documento de destino, você precisa definir a opção`SectionStart` propriedade da primeira seção no documento de origem para`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Etapa 4: definir a formatação de parágrafo "Manter com o próximo" para o documento de origem

 Para manter os parágrafos do documento de origem juntos, você pode percorrer cada parágrafo do documento e definir o`KeepWithNext`propriedade para`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Etapa 5: anexar o documento de origem ao documento de destino

 Agora, você pode anexar o documento de origem ao documento de destino usando o`AppendDocument` método do`Document` aula. O`ImportFormatMode.KeepSourceFormatting` O parâmetro garante que a formatação de origem seja preservada durante a operação de acréscimo.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 6: salve o documento final

 Por fim, salve o documento mesclado com o recurso "Keep Source Together" habilitado usando o`Save` método do`Document` aula.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Exemplo de código-fonte para Keep Source Together usando Aspose.Words for .NET 

Aqui está o código-fonte completo do recurso "Keep Source Together" em C# usando Aspose.Words for .NET:


```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Defina o documento de origem para aparecer logo após o conteúdo do documento de destino.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

É isso! Você implementou com sucesso o recurso Keep Source Together usando Aspose.Words for .NET. O documento final conterá o conteúdo mesclado com os parágrafos do documento de origem mantidos juntos.