---
title: Anexar documento ao espaço em branco
linktitle: Anexar documento ao espaço em branco
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como anexar um documento a um documento de destino em branco no Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/append-document-to-blank/
---

Este tutorial explica como usar Aspose.Words for .NET para anexar o conteúdo de um documento a um documento de destino em branco. O código-fonte fornecido demonstra como criar um novo documento, remover seu conteúdo e, em seguida, anexar o documento de origem a ele.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

-  Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo em[Aspose.Releases]https://releases.aspose.com/words/net/ ou use o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório de documentos onde os documentos de origem e destino estão localizados.

## Passo 2: Crie um novo documento de destino

 Crie um novo`Document` objeto para o documento de destino.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Etapa 3: remover o conteúdo existente do documento de destino

 Para garantir um documento de destino limpo, remova todo o conteúdo existente do documento usando o`RemoveAllChildren` método.

```csharp
dstDoc.RemoveAllChildren();
```

## Etapa 4: anexar o documento de origem ao documento de destino

 Anexe o conteúdo do documento de origem ao documento de destino usando o comando`AppendDocument` método com`ImportFormatMode.KeepSourceFormatting` opção.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Etapa 5: salve o documento de destino

Finalmente, salve o documento de destino modificado usando o`Save` método do`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Isso completa a implementação de anexar um documento a um documento de destino em branco usando Aspose.Words for .NET.

### Exemplo de código-fonte para Append Document To Blank usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// O documento de destino não está vazio, muitas vezes fazendo com que uma página em branco apareça antes do documento anexado.
	// Isso ocorre porque o documento base possui uma seção vazia e o novo documento é iniciado na próxima página.
	// Remova todo o conteúdo do documento de destino antes de anexar.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```