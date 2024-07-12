---
title: Zaškrtávací políčko Typ řízení obsahu
linktitle: Zaškrtávací políčko Typ řízení obsahu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit obsah zaškrtávacího pole Type Control v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/check-box-type-content-control/
---

Tento výukový program vysvětluje, jak vytvořit ovládací prvek obsahu typu zaškrtávací políčko v dokumentu aplikace Word pomocí Aspose.Words for .NET. Ovládací prvky obsahu zaškrtávacích políček umožňují uživatelům vybrat nebo zrušit zaškrtnutí políčka v dokumentu.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"`se skutečnou cestou k adresáři, kam chcete dokument uložit.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte dokument a DocumentBuilder
 Vytvořte novou instanci souboru`Document` třída a a`DocumentBuilder` k vytvoření obsahu dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Přidejte zaškrtávací políčko Typ řízení obsahu
 Vytvořit`StructuredDocumentTag` s`SdtType.Checkbox` reprezentovat ovládací prvek obsahu zaškrtávacího políčka. Upřesněte`MarkupLevel.Inline` umístit jej do textu.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Krok 4: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save`metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako „WorkingWithSdt.CheckBoxTypeContentControl.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Příklad zdrojového kódu pro zaškrtávací pole Type Content Control pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

A je to! Úspěšně jste vytvořili ovládací prvek obsahu zaškrtávacího políčka ve vašem dokumentu aplikace Word pomocí Aspose.Words for .NET.