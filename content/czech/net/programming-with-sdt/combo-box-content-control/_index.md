---
title: Combo Box Content Control
linktitle: Combo Box Content Control
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit Combo Box Content Control v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/combo-box-content-control/
---

Tento kurz vysvětluje, jak vytvořit Combo Box Content Control v dokumentu aplikace Word pomocí Aspose.Words for .NET. Ovládací prvky obsahu pole se seznamem umožňují uživatelům vybrat položku z rozevíracího seznamu.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kam chcete dokument uložit.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte dokument a StructuredDocumentTag
 Vytvořte novou instanci souboru`Document` třída a a`StructuredDocumentTag` reprezentovat ovládací prvek obsahu pole se seznamem. Upřesněte`SdtType.ComboBox` jako typ a`MarkupLevel.Block` jako úroveň označení pro vytvoření pole se seznamem na úrovni bloku.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Krok 3: Přidejte položky do Combo Boxu
 Přidejte položky do pole se seznamem pomocí`ListItems` vlastnictvím`StructuredDocumentTag` Každá položka je reprezentována a`SdtListItem` objekt, který přebírá zobrazovaný text a hodnotu. V tomto příkladu přidáme tři položky do pole se seznamem.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Krok 4: Připojte StructuredDocumentTag k dokumentu
 Připojte ovládací prvek obsahu pole se seznamem k tělu dokumentu pomocí`AppendChild` metoda těla první části dokumentu.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Krok 5: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu uložíme dokument jako "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Příklad zdrojového kódu pro Combo Box Content Control pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

A je to! Úspěšně jste vytvořili Combo Box Content Control ve vašem dokumentu Word pomocí Aspose.Words for .NET.