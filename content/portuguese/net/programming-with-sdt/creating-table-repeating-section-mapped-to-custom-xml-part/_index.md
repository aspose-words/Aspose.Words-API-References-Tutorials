---
title: Criando seção de repetição de tabela mapeada para parte XML personalizada
linktitle: Criando seção de repetição de tabela mapeada para parte XML personalizada
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como criar uma tabela com uma seção repetida mapeada para um CustomXmlPart em um documento do Word usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---
## Introdução

Neste tutorial, percorreremos o processo de criação de uma tabela com uma seção repetida que é mapeada para uma parte XML personalizada usando Aspose.Words for .NET. Isto é particularmente útil para gerar documentos dinamicamente com base em dados estruturados.

## Pré-requisitos

Antes de começarmos, certifique-se de ter o seguinte:
1.  Biblioteca Aspose.Words para .NET instalada. Você pode baixá-lo no[Aspor site](https://releases.aspose.com/words/net/).
2. Uma compreensão básica de C# e XML.

## Importar namespaces

Certifique-se de incluir os namespaces necessários em seu projeto:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Tables;
```

## Etapa 1: inicializar o documento e o DocumentBuilder

 Primeiro, crie um novo documento e inicialize um`DocumentBuilder`:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: adicionar parte XML personalizada

Adicione uma parte XML personalizada ao documento. Este XML contém os dados que queremos mapear para nossa tabela:

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
    "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
    "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Etapa 3: Crie a estrutura da tabela

 A seguir, use o`DocumentBuilder` para criar o cabeçalho da tabela:

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Etapa 4: criar seção repetitiva

 Crie um`StructuredDocumentTag` (SDT) para a seção de repetição e mapeie-a para os dados XML:

```csharp
StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Etapa 5: criar um item de seção repetitivo

Crie um SDT para o item da seção de repetição e adicione-o à seção de repetição:

```csharp
StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Etapa 6: mapear dados XML para células da tabela

Crie SDTs para o título e o autor, mapeie-os para os dados XML e anexe-os à linha:

```csharp
StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Etapa 7: salve o documento

Finalmente, salve o documento no diretório especificado:

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

## Conclusão

Seguindo essas etapas, você criou com êxito uma tabela com uma seção de repetição mapeada para uma parte XML personalizada usando Aspose.Words for .NET. Isto permite a geração dinâmica de conteúdo com base em dados estruturados, tornando a criação de documentos mais flexível e poderosa.

## Perguntas frequentes

### O que é uma StructuredDocumentTag (SDT)?
Um SDT, também conhecido como controle de conteúdo, é uma região delimitada em um documento usada para conter dados estruturados.

### Posso usar outros tipos de dados na parte XML personalizada?
Sim, você pode estruturar sua parte XML personalizada com qualquer tipo de dados e mapeá-los adequadamente.

### Como adiciono mais linhas à seção de repetição?
A seção de repetição replica automaticamente a estrutura de linha para cada item no caminho XML mapeado.