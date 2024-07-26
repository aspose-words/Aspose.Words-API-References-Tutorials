---
title: Přidat tvar skupiny
linktitle: Přidat tvar skupiny
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak přidat tvar skupiny s více tvary do dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-shapes/add-group-shape/
---

Tento tutoriál vysvětluje, jak přidat tvar skupiny obsahující více tvarů do dokumentu aplikace Word pomocí Aspose.Words for .NET. Skupinové tvary umožňují kombinovat a manipulovat s více tvary jako s jedinou entitou.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kam chcete dokument uložit.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte nový dokument a GroupShape
 Vytvořte novou instanci souboru`Document` třída a`GroupShape` objekt pracovat s dokumentem.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Krok 3: Vytvořte a přidejte tvary do GroupShape
 Vytvářejte jednotlivé tvary jako např`accentBorderShape`a`actionButtonShape` za použití`Shape` třída. Upravte jejich vlastnosti podle potřeby. Připojte tyto tvary k`groupShape` objekt.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Krok 4: Nastavte rozměry pro GroupShape
 Nastavte šířku, výšku a velikost souřadnic pro`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Krok 5: Vložte GroupShape do dokumentu
 Vytvořit`DocumentBuilder` objekt a vložte jej`groupShape` do dokumentu pomocí`InsertNode` metoda.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Krok 6: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu uložíme dokument jako "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Příklad zdrojového kódu pro Add Group Shape pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

je to! Úspěšně jste přidali tvar skupiny obsahující více tvarů do dokumentu aplikace Word pomocí Aspose.W