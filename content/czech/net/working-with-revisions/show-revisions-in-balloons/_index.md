---
title: Zobrazit revize v bublinách
linktitle: Zobrazit revize v bublinách
second_title: Aspose.Words API pro zpracování dokumentů
description: Zobrazit revize v bublinách pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/working-with-revisions/show-revisions-in-balloons/
---

V tomto podrobném průvodci vám ukážeme, jak zobrazit revize v bublinách v dokumentu aplikace Word pomocí Aspose.Words for .NET. Poskytneme vám kompletní zdrojový kód a ukážeme vám, jak formátovat výstup markdown.

## Krok 1: Načtení dokumentu

Prvním krokem je nahrání dokumentu obsahujícího revize.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Krok 2: Nakonfigurujte možnosti zobrazení recenze

Nakonfigurujeme možnosti zobrazení tak, aby byly revize viditelné v bublinách.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Krok 3: Uložte dokument ve formátu PDF

Nakonec dokument uložíme jako PDF s revizemi zobrazenými v bublinách.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Výstupní formáty Markdown

Výstup lze formátovat v markdown pro zlepšení čitelnosti. Například :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Příklad zdrojového kódu pro Show Revisions In Balloons pomocí Aspose.Words for .NET

Zde je úplný zdrojový kód pro zobrazení revizí v bublinách v dokumentu pomocí Aspose.Words pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Vykresluje vložené revize, odstraňuje a formátuje revize v pozicích.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Vykreslí revizní pruhy na pravé straně stránky.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Závěr

tomto tutoriálu jsme se naučili, jak zobrazit revize v bublinách v dokumentu aplikace Word pomocí Aspose.Words for .NET. Pomocí vhodných možností zobrazení jsme byli schopni zviditelnit revize v bublinách s revizními pruhy na pravé straně. Aspose.Words for .NET nabízí mnoho výkonných funkcí pro manipulaci s dokumenty Word, včetně správy revizí. Nyní můžete tyto znalosti použít k zobrazení revizí v bublinách ve vašich vlastních dokumentech aplikace Word pomocí Aspose.Words for .NET.


### FAQ

#### Otázka: Jak nahrát dokument do Aspose.Words pro .NET?

 A: Použijte`Document` třídy Aspose.Words pro .NET k načtení dokumentu ze souboru. Můžete zadat úplnou cestu dokumentu.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Otázka: Jak zobrazit revize v bublinách pomocí Aspose.Words pro .NET?

 A: Použijte`ShowInBalloons` vlastnictvím`RevisionOptions` objekt pro konfiguraci zobrazení revizí v bublinách. Tuto vlastnost můžete zapnout`ShowInBalloons.FormatAndDelete` k zobrazení revizí v bublinách s revizemi odstranění a formátování.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Otázka: Jak uložit dokument ve formátu PDF pomocí Aspose.Words pro .NET?

 A: Použijte`Save` metoda`Document` objekt pro uložení dokumentu ve formátu PDF. Musíte zadat úplnou cílovou cestu s příponou „.pdf“.

```csharp
doc.Save("path/to/destination/document.pdf");
```