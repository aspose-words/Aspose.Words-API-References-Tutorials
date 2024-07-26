---
title: Svázat SDT s vlastní částí XML
linktitle: Svázat SDT s vlastní částí XML
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak svázat SDT s vlastní částí XML pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Tento tutoriál ukazuje, jak svázat značku strukturovaného dokumentu (SDT) s vlastní částí XML pomocí Aspose.Words for .NET. SDT umožňují přidat do dokumentu aplikace Word ovládací prvky strukturovaného obsahu a CustomXmlParts poskytují způsob, jak uložit vlastní data XML spojená s dokumentem.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a XML.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kam chcete dokument uložit.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte dokument a CustomXmlPart
 Vytvořte novou instanci souboru`Document` třída a a`CustomXmlPart` pro uložení vlastních dat XML. Vlastní XML by mělo být v platném formátu XML. V tomto příkladu používáme jednoduchý řetězec XML`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Krok 3: Přidejte do dokumentu StructuredDocumentTag (SDT).
 Přidat`StructuredDocumentTag`do dokumentu, aby sloužil jako kontrola obsahu. Určete`SdtType` tak jako`PlainText` a`MarkupLevel` tak jako`Block` vytvořit SDT na úrovni bloku.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Krok 4: Nastavte mapování XML pro SDT
 Mapujte SDT na`CustomXmlPart` pomocí`SetMapping` metoda`XmlMapping` vlastnictví. Určete`CustomXmlPart` , výraz XPath k nalezení požadovaného uzlu XML a v případě potřeby předponu oboru názvů. V tomto příkladu mapujeme SDT na`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Krok 5: Uložte dokument
 Uložte upravený dokument do zadaného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Příklad zdrojového kódu pro Bind Sd Tto Custom Xml Part pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

A je to! Úspěšně jste svázali SDT s CustomXmlPart ve vašem dokumentu Word pomocí Aspose.Words for .NET.