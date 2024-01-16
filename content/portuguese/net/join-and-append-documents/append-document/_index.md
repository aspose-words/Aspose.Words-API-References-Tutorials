---
title: Anexar documento
linktitle: Anexar documento
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como anexar o conteúdo de um documento a outro usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/join-and-append-documents/append-document/
---

Este tutorial explica como usar Aspose.Words for .NET para anexar o conteúdo de um documento a outro. O código-fonte fornecido demonstra como abrir os documentos de origem e destino, importar e anexar seções do documento de origem ao documento de destino.

## Etapa 1: configurar o projeto

Certifique-se de ter os seguintes pré-requisitos:

-  Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo em[Aspose.Releases]https://releases.aspose.com/words/net/ ou use o gerenciador de pacotes NuGet para instalá-lo.
- Um caminho do diretório de documentos onde os documentos de origem e destino estão localizados.

## Passo 2: Abra os documentos de origem e destino

 Abra os documentos de origem e destino usando o`Document` construtor de classe. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório do seu documento.

```csharp
// Caminho para o diretório do seu documento
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Etapa 3: anexar seções do documento de origem ao documento de destino

 Percorra todas as seções do documento de origem e importe cada seção para o documento de destino usando o`ImportNode` método. Em seguida, anexe a seção importada ao documento de destino.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Etapa 4: salve o documento de destino

 Finalmente, salve o documento de destino modificado usando o`Save` método do`Document` objeto.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Isso conclui a implementação de anexar um documento usando Aspose.Words for .NET.

### Exemplo de código-fonte para anexar documento usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Percorra todas as seções do documento de origem.
	//Os nós de seção são filhos imediatos do nó Documento, portanto podemos apenas enumerar o Documento.
	foreach (Section srcSection in srcDoc)
	{
		// Como estamos copiando uma seção de um documento para outro,
		// é necessário importar o nó Seção para o documento de destino.
		// Isso ajusta quaisquer referências específicas do documento a estilos, listas, etc.
		//
		// A importação de um nó cria uma cópia do nó original, mas a cópia
		// ss pronto para ser inserido no documento de destino.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Agora o novo nó de seção pode ser anexado ao documento de destino.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```