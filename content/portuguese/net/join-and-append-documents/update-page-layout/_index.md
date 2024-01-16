---
title: Atualizar layout de página
linktitle: Atualizar layout de página
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como atualizar o layout da página ao juntar e anexar documentos do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/update-page-layout/
---

Este tutorial irá guiá-lo através do processo de uso do recurso Atualizar layout de página do Aspose.Words for .NET. Este recurso garante que o layout da página seja atualizado corretamente ao juntar e anexar documentos do Word.

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

## Etapa 3: atualizar o layout da página do documento de destino

 Para garantir que o layout da página seja atualizado corretamente antes de anexar o documento de origem, você pode chamar o método`UpdatePageLayout` método no documento de destino.

```csharp
dstDoc.UpdatePageLayout();
```

## Etapa 4: anexar o documento de origem ao documento de destino

 Agora, você pode anexar o documento de origem ao documento de destino usando o`AppendDocument` método do`Document` aula. O`ImportFormatMode.KeepSourceFormatting` O parâmetro garante que a formatação de origem seja preservada durante a operação de acréscimo.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 5: atualize o layout da página novamente

 Depois de anexar o documento de origem, você precisa chamar o`UpdatePageLayout`no documento de destino novamente para garantir que quaisquer alterações feitas após a operação de acréscimo sejam refletidas na saída renderizada.

```csharp
dstDoc.UpdatePageLayout();
```

## Etapa 6: salve o documento final

 Por fim, salve o documento mesclado com o recurso Atualizar layout de página ativado usando o`Save` método do`Document` aula.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Exemplo de código-fonte para atualizar layout de página usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso "Atualizar layout de página" em C# usando Aspose.Words for .NET:

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Se o documento de destino for renderizado em PDF, imagem etc.
	// ou UpdatePageLayout é chamado antes do documento de origem. Está anexado,
	// então quaisquer alterações feitas depois não serão refletidas na saída renderizada
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Para que as alterações sejam atualizadas na saída renderizada, UpdatePageLayout deve ser chamado novamente.
	// Se não for chamado novamente, o documento anexado não aparecerá na saída da próxima renderização.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

É isso! Você implementou com sucesso o recurso Atualizar layout de página usando Aspose.Words for .NET. O documento final conterá o conteúdo mesclado com o layout da página atualizado corretamente.