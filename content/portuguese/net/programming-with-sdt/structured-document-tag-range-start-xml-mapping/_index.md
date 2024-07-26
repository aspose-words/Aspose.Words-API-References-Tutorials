---
title: Mapeamento Xml inicial do intervalo de tags do documento estruturado
linktitle: Mapeamento Xml inicial do intervalo de tags do documento estruturado
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como configurar o mapeamento XML para um intervalo de tags de documento estruturado iniciado em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Este tutorial explica como configurar o mapeamento XML para um intervalo de tags de documento estruturado iniciado em um documento do Word usando Aspose.Words for .NET. O mapeamento XML permite exibir partes específicas de uma fonte de dados XML no controle de conteúdo.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde seu documento está localizado.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: carregar o documento e criar parte XML
 Carregue o documento do Word usando o`Document` construtor, passando o caminho para o documento como parâmetro. Crie uma parte XML que contenha os dados que você deseja exibir na tag do documento estruturado.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Etapa 3: definir mapeamento XML para tag de documento estruturado
Recuperar o intervalo de tags do documento estruturado a partir do documento. Em seguida, configure o mapeamento XML para a tag do documento estruturado para exibir uma parte específica da parte XML customizada usando uma expressão XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Etapa 4: salve o documento
 Salve o documento modificado no diretório especificado usando o`Save`método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Exemplo de código-fonte para intervalo de tags de documento estruturado Iniciar mapeamento Xml usando Aspose.Words para .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Construa uma parte XML que contenha dados e adicione-a à coleção CustomXmlPart do documento.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Crie uma StructuredDocumentTag que exibirá o conteúdo de nossa CustomXmlPart no documento.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Se definirmos um mapeamento para nossa StructuredDocumentTag,
	// ele exibirá apenas uma parte do CustomXmlPart para a qual o XPath aponta.
	// Este XPath apontará para o segundo elemento "<text>" do conteúdo do primeiro elemento "<root>" de nosso CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

É isso! Você configurou com êxito o mapeamento XML para um intervalo de tags de documento estruturado iniciado em seu documento do Word usando Aspose.Words for .NET.