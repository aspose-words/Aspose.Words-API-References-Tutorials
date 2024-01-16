---
title: Řízení obsahu formátovaného textového pole
linktitle: Řízení obsahu formátovaného textového pole
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vytvořit ovládací prvek obsahu pole s formátovaným textem v dokumentu aplikace Word pomocí Aspose.Words for .NET umožňující formátování a stylování textu.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/rich-text-box-content-control/
---

Tento kurz ukazuje, jak vytvořit ovládací prvek obsahu pole s formátovaným textem v dokumentu aplikace Word pomocí Aspose.Words for .NET. Ovládací prvky obsahu formátovaného textového pole umožňují uživatelům zadávat a formátovat text pomocí různých stylů a možností formátování.

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
 Vytvořte novou instanci souboru`Document` třída a a`StructuredDocumentTag` reprezentovat ovládací prvek obsahu pole s formátovaným textem. Upřesněte`SdtType.RichText` jako typ a`MarkupLevel.Block` jako úroveň označení pro vytvoření pole formátovaného textu na úrovni bloku.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Krok 3: Vytvořte a naformátujte obsah RTF
Vytvořte odstavec a spusťte jej tak, aby představoval obsah formátovaného textu. Nastavte možnosti textu a formátování, jako je barva, písmo atd.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Krok 4: Přidejte obsah ve formátu RTF do ovládacího prvku obsahu
Přidejte odstavec s obsahem formátovaného textu do`ChildNodes` kolekce ovládacího prvku obsahu pole s formátovaným textem.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Krok 5: Připojte ovládací prvek obsahu k dokumentu
 Připojte ovládací prvek obsahu pole s formátovaným textem k tělu dokumentu pomocí`AppendChild` metoda těla první části dokumentu.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Krok 6: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu uložíme dokument jako "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Příklad zdrojového kódu pro řízení obsahu RTF pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

A je to! Úspěšně jste vytvořili ovládací prvek obsahu pole s formátovaným textem v dokumentu aplikace Word pomocí Aspose.Words for .NET.