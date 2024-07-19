---
title: Aktuální stav zaškrtávacího políčka
linktitle: Aktuální stav zaškrtávacího políčka
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak načíst a nastavit aktuální stav ovládacího prvku obsahu zaškrtávacího políčka v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/current-state-of-check-box/
---

Tento výukový program vysvětluje, jak načíst a nastavit aktuální stav ovládacího prvku obsahu zaškrtávacího políčka v dokumentu aplikace Word pomocí Aspose.Words for .NET. Zaškrtávací políčko můžete zaškrtnout nebo zrušit podle jeho aktuálního stavu.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vložte dokument a získejte kontrolu obsahu zaškrtávacího políčka
 Načtěte dokument aplikace Word pomocí`Document` konstruktor, předá cestu k dokumentu jako parametr. Poté z dokumentu načtěte požadovaný ovládací prvek obsahu zaškrtávacího políčka. V tomto příkladu předpokládáme, že zaškrtávací políčko je první značkou strukturovaného dokumentu v dokumentu.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Krok 3: Zaškrtněte nebo zrušte zaškrtnutí políčka na základě jeho aktuálního stavu
 Zkontrolujte, zda je načtená značka strukturovaného dokumentu typu`SdtType.Checkbox` . Pokud je, nastavte`Checked` vlastnost ovládacího prvku obsahu na`true` pro zaškrtnutí políčka. V opačném případě ji můžete nechat nezaškrtnutou.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Krok 4: Uložte dokument
 Uložte upravený dokument do zadaného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako „WorkingWithSdt.CurrentStateOfCheckBox.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Příklad zdrojového kódu pro aktuální stav zaškrtávacího políčka pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Získejte první ovládací prvek obsahu z dokumentu.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

A je to! Úspěšně jste načetli a nastavili aktuální stav kontroly obsahu zaškrtávacího políčka ve vašem dokumentu Word pomocí Aspose.Words for .NET.