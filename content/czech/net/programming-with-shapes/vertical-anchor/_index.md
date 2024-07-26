---
title: Vertikální kotva
linktitle: Vertikální kotva
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak umístit tvar svisle v dokumentu pomocí funkce svislého ukotvení v Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-shapes/vertical-anchor/
---

Tento výukový program vysvětluje, jak používat funkci svislého ukotvení v Aspose.Words pro .NET k umístění tvaru svisle v dokumentu. Nastavením vlastnosti vertikálního ukotvení tvaru můžete ovládat jeho vertikální zarovnání vzhledem k textu nebo stránce.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kam chcete dokument uložit.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte nový dokument a DocumentBuilder
 Vytvořte novou instanci souboru`Document` třída a a`DocumentBuilder` objekt pracovat s dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vložte a nakonfigurujte tvar
 Vložte tvar do dokumentu pomocí`InsertShape` metoda`DocumentBuilder` objekt. Nastavte požadované rozměry tvaru.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Krok 4: Nastavte vertikální kotvu
Nastavte vlastnost vertikálního ukotvení tvaru, abyste řídili jeho vertikální zarovnání. V tomto příkladu jsme jej nastavili na „Dol“, abychom tvar ukotvili ve spodní části textu nebo stránky.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Krok 5: Přidejte obsah do tvaru
 Použijte`MoveTo` metoda`DocumentBuilder` objekt přesunout kurzor na první odstavec tvaru. Poté použijte`Write` způsob přidání obsahu do tvaru.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Krok 6: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu uložíme dokument jako "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Příklad zdrojového kódu pro Vertical Anchor pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

A je to! Úspěšně jste použili funkci svislého ukotvení v Aspose.Words pro .NET k umístění tvaru svisle v dokumentu.