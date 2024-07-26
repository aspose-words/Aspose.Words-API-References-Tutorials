---
title: Vytvoření části opakování tabulky mapované na vlastní část XML
linktitle: Vytvoření části opakování tabulky mapované na vlastní část XML
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit tabulku s opakující se částí namapovanou na CustomXmlPart v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Tento tutoriál ukazuje, jak vytvořit tabulku s opakující se částí mapovanou na vlastní část XML v dokumentu aplikace Word pomocí Aspose.Words for .NET. Opakující se část vám umožňuje dynamicky přidávat řádky na základě dat XML uložených ve vlastní části Xml.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kam chcete dokument uložit.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte dokument a DocumentBuilder
 Vytvořte novou instanci souboru`Document` třída a a`DocumentBuilder` k vytvoření obsahu dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Přidejte vlastní data XML do CustomXmlPart
 Vytvořit`CustomXmlPart` a přidat do něj vlastní data XML. V tomto příkladu vytvoříme řetězec XML představující kolekci knih s jejich názvy a autory.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Krok 4: Vytvořte tabulku a strukturu tabulky
Začněte vytvářet tabulku pomocí`StartTable` metoda`DocumentBuilder` . Přidejte buňky tabulky a obsah pomocí`InsertCell`a`Write` metody.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Krok 5: Vytvořte opakující se oddíl namapovaný na vlastní XML
 Vytvořit`StructuredDocumentTag` s`SdtType.RepeatingSection` reprezentovat opakující se část. Nastavte mapování XML pro opakující se sekci pomocí`SetMapping` metoda`XmlMapping` vlastnictví. V tomto příkladu mapujeme opakující se sekci na`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Krok 6: Vytvořte položku Opakující se sekce a přidejte buňky
 Vytvořit`StructuredDocumentTag` s`SdtType.RepeatingSectionItem` reprezentovat opakující se položku sekce. Připojte jej jako dítě do opakující se části.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Vytvořit`Row` reprezentovat každou položku v opakující se sekci a připojit ji k položce opakující se sekce.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Krok 7: Přidejte ovládací prvky obsahu do sekce opakování
 Vytvořit`StructuredDocumentTag` předměty s`SdtType.PlainText`

  reprezentovat název a ovládací prvky obsahu autora. Nastavte mapování XML pro každý ovládací prvek obsahu pomocí`SetMapping` metoda`XmlMapping` vlastnictví. V tomto příkladu mapujeme ovládací prvek title na`/books[1]/book[1]/title[1]` a autor to řídí`/books[1]/book[1]/author[1]`.

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

## Krok 8: Uložte dokument
 Uložte upravený dokument do zadaného adresáře pomocí`Save`metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Příklad zdrojového kódu pro vytvoření části s opakováním tabulky namapované na vlastní část XML pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
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

A je to! Úspěšně jste vytvořili tabulku s opakující se částí namapovanou na CustomXmlPart ve vašem dokumentu Word pomocí Aspose.Words for .NET.