---
title: Nastavit styl ovládání obsahu
linktitle: Nastavit styl ovládání obsahu
second_title: Aspose.Words API pro zpracování dokumentů
description: Zjistěte, jak nastavit styl ovládacího prvku obsahu v dokumentu aplikace Word pomocí Aspose.Words for .NET a použít konzistentní formátování.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/set-content-control-style/
---

Tento tutoriál vysvětluje, jak nastavit styl ovládacího prvku obsahu v dokumentu aplikace Word pomocí Aspose.Words for .NET. Na ovládací prvky obsahu můžete použít předdefinované nebo vlastní styly pro konzistentní formátování.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte dokument a získejte kontrolu obsahu
 Načtěte dokument aplikace Word pomocí`Document`konstruktor, předá cestu k dokumentu jako parametr. Načtěte požadovaný ovládací prvek obsahu z dokumentu. V tomto příkladu předpokládáme, že ovládací prvek obsahu je první značkou strukturovaného dokumentu v dokumentu.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Krok 3: Načtěte styl a použijte jej na kontrolu obsahu
 Získejte požadovaný styl z kolekce stylů dokumentu. V tomto příkladu načteme styl "Citace" pomocí`StyleIdentifier.Quote` . Poté přiřaďte načtený styl k`Style` vlastnost tagu strukturovaného dokumentu.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Krok 4: Uložte dokument
 Uložte upravený dokument do zadaného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Příklad zdrojového kódu pro Set Content Control Style pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

A je to! Úspěšně jste nastavili styl ovládacího prvku obsahu v dokumentu aplikace Word pomocí Aspose.Words for .NET.