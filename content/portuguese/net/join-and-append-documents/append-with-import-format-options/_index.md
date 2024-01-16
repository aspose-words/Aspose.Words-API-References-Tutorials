---
title: Anexar com opções de formato de importação
linktitle: Anexar com opções de formato de importação
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como anexar um documento com opções de formato de importação usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/append-with-import-format-options/
---

Este tutorial explica como usar Aspose.Words for .NET para anexar o conteúdo de um documento a outro com opções de formato de importação. O código-fonte fornecido demonstra como abrir os documentos de origem e de destino, especificar opções de formato de importação e anexar o documento de origem ao documento de destino.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

-  Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo em[Aspose.Releases]https://releases.aspose.com/words/net/ ou use o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório de documentos onde os documentos de origem e destino estão localizados.

## Passo 2: Abra os documentos de origem e destino

 Abra os documentos de origem e destino usando o`Document` construtor de classe. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Etapa 3: especifique as opções de formato de importação

 Crie uma instância do`ImportFormatOptions` class para especificar as opções de formato de importação. Neste exemplo, usamos o`KeepSourceNumbering` propriedade para garantir que a numeração do documento de origem seja usada se houver conflitos com o documento de destino.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Etapa 4: anexar o documento de origem ao documento de destino

 Use o`AppendDocument` método do documento de destino para anexar o documento de origem. Passar`ImportFormatMode.UseDestinationStyles` como o segundo parâmetro para usar os estilos e a formatação do documento de destino.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Etapa 5: salve o documento de destino

 Finalmente, salve o documento de destino modificado usando o`Save` método do`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Isso conclui a implementação de anexar um documento com opções de formato de importação usando Aspose.Words for .NET.

### Exemplo de código-fonte para anexar com opções de formato de importação usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Especifique que se a numeração entrar em conflito nos documentos de origem e de destino,
	//então será usada a numeração do documento de origem.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```