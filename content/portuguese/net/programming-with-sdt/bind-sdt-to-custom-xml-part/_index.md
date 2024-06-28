---
title: Vincular SDT à parte XML personalizada
linktitle: Vincular SDT à parte XML personalizada
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como vincular um SDT a uma parte XML personalizada usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Este tutorial demonstra como vincular uma tag de documento estruturado (SDT) a uma parte Xml personalizada usando Aspose.Words for .NET. SDTs permitem adicionar controles de conteúdo estruturados a um documento do Word, e CustomXmlParts fornecem uma maneira de armazenar dados XML personalizados associados ao documento.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e XML.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: criar um documento e CustomXmlPart
 Crie uma nova instância do`Document` aula e um`CustomXmlPart` para armazenar os dados XML personalizados. O XML customizado deve estar em formato XML válido. Neste exemplo, usamos uma string XML simples`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Etapa 3: adicionar uma StructuredDocumentTag (SDT) ao documento
 Adicione um`StructuredDocumentTag` ao documento para servir como controle de conteúdo. Especifique o`SdtType` como`PlainText` e a`MarkupLevel` como`Block` para criar um SDT em nível de bloco.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Etapa 4: definir o mapeamento XML para o SDT
 Mapeie o SDT para o`CustomXmlPart` usando o`SetMapping` método do`XmlMapping` propriedade. Especifique o`CustomXmlPart` , a expressão XPath para localizar o nó XML desejado e o prefixo do namespace, se necessário. Neste exemplo, mapeamos o SDT para`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Etapa 5: salve o documento
 Salve o documento modificado no diretório especificado usando o`Save` método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Exemplo de código-fonte para Bind Sd Tto Custom Xml Part usando Aspose.Words for .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

É isso! Você vinculou com êxito um SDT a um CustomXmlPart em seu documento do Word usando Aspose.Words for .NET.