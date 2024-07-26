---
title: Criando seção de repetição de tabela mapeada para parte XML personalizada
linktitle: Criando seção de repetição de tabela mapeada para parte XML personalizada
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar uma tabela com uma seção repetida mapeada para um CustomXmlPart em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Este tutorial demonstra como criar uma tabela com uma seção repetida mapeada para uma parte Xml personalizada em um documento do Word usando Aspose.Words for .NET. A seção de repetição permite adicionar linhas dinamicamente com base nos dados XML armazenados na parte XML personalizada.

## Pré-requisitos
Para seguir este tutorial, você precisa ter o seguinte:

- Biblioteca Aspose.Words para .NET instalada.
- Conhecimento básico de C# e processamento de palavras com documentos Word.

## Etapa 1: configurar o diretório de documentos
 Comece configurando o caminho para o diretório do seu documento. Substituir`"YOUR DOCUMENT DIRECTORY"` com o caminho real para o diretório onde você deseja salvar o documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Etapa 2: Crie um Documento e DocumentBuilder
 Crie uma nova instância do`Document` aula e um`DocumentBuilder` para construir o conteúdo do documento.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: adicionar dados XML personalizados a um CustomXmlPart
 Criar uma`CustomXmlPart` e adicione dados XML personalizados a ele. Neste exemplo, criamos uma string XML representando uma coleção de livros com seus títulos e autores.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Etapa 4: criar uma tabela e uma estrutura de tabela
Comece a criar uma tabela usando o`StartTable` método do`DocumentBuilder` . Adicione células e conteúdo da tabela usando o`InsertCell`e`Write` métodos.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Etapa 5: Crie a seção de repetição mapeada para XML personalizado
 Criar uma`StructuredDocumentTag` com`SdtType.RepeatingSection` para representar a seção repetida. Defina o mapeamento XML para a seção de repetição usando o comando`SetMapping` método do`XmlMapping` propriedade. Neste exemplo, mapeamos a seção de repetição para`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Etapa 6: crie o item de seção repetitiva e adicione células
 Criar uma`StructuredDocumentTag` com`SdtType.RepeatingSectionItem` para representar o item da seção repetida. Anexe-o como uma criança à seção de repetição.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Criar uma`Row` para representar cada item na seção de repetição e anexá-lo ao item da seção de repetição.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Etapa 7: adicionar controles de conteúdo na seção de repetição
 Criar`StructuredDocumentTag` objetos com`SdtType.PlainText`

  para representar os controles de título e conteúdo do autor. Defina o mapeamento XML para cada controle de conteúdo usando o comando`SetMapping` método do`XmlMapping` propriedade. Neste exemplo, mapeamos o controle de título para`/books[1]/book[1]/title[1]` e o controle do autor para`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Etapa 8: salve o documento
 Salve o documento modificado no diretório especificado usando o`Save`método. Forneça o nome de arquivo desejado com a extensão de arquivo apropriada. Neste exemplo, salvamos o documento como "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Exemplo de código-fonte para criação de seção de repetição de tabela mapeada para parte XML personalizada usando Aspose.Words para .NET 

```csharp
	// Caminho para o diretório do seu documento
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

É isso! Você criou com sucesso uma tabela com uma seção de repetição mapeada para um CustomXmlPart em seu documento do Word usando Aspose.Words for .NET.