---
title: Rozsah tagů strukturovaného dokumentu Spusťte mapování XML
linktitle: Rozsah tagů strukturovaného dokumentu Spusťte mapování XML
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit mapování XML pro začátek rozsahu značek strukturovaného dokumentu v dokumentu Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Tento tutoriál vysvětluje, jak nastavit mapování XML pro začátek rozsahu značek strukturovaného dokumentu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Mapování XML umožňuje zobrazit konkrétní části zdroje dat XML v rámci ovládacího prvku obsahu.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte dokument a vytvořte část XML
 Načtěte dokument aplikace Word pomocí`Document` konstruktor, předá cestu k dokumentu jako parametr. Vytvořte část XML, která obsahuje data, která chcete zobrazit ve značce strukturovaného dokumentu.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Krok 3: Nastavte mapování XML pro značku strukturovaného dokumentu
Načtěte rozsah značek strukturovaného dokumentu začněte od dokumentu. Potom nastavte mapování XML pro značku strukturovaného dokumentu tak, aby zobrazovalo konkrétní část vlastní části XML pomocí výrazu XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Krok 4: Uložte dokument
 Uložte upravený dokument do zadaného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako „WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Příklad zdrojového kódu pro Structured Document Tag Range Spustit mapování XML pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Vytvořte část XML, která obsahuje data, a přidejte ji do kolekce CustomXmlPart dokumentu.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Vytvořte StructuredDocumentTag, který zobrazí obsah naší CustomXmlPart v dokumentu.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Pokud nastavíme mapování pro náš StructuredDocumentTag,
	// zobrazí pouze část CustomXmlPart, na kterou XPath ukazuje.
	// Tato cesta XPath bude ukazovat na obsah druhého prvku „<text>“ prvního prvku „<root>“ naší CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

je to! Úspěšně jste nastavili mapování XML pro začátek rozsahu značek strukturovaného dokumentu ve vašem dokumentu Word pomocí Aspose.Words for .NET.