---
title: Otevřené funkce typu
linktitle: Otevřené funkce typu
second_title: Aspose.Words API pro zpracování dokumentů
description: Přečtěte si, jak povolit a používat funkce Open Type v Aspose.Words for .NET
type: docs
weight: 10
url: /cs/net/enable-opentype-features/open-type-features/
---

tomto komplexním tutoriálu se dozvíte, jak povolit a využívat funkce Open Type v Aspose.Words pro .NET. Provedeme vás celým procesem a poskytneme vám potřebné úryvky kódu C#. Na konci této příručky budete schopni pracovat s funkcemi Open Type v dokumentech aplikace Word.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Vložte dokument
Chcete-li začít, načtěte dokument pomocí třídy Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Krok 2: Povolte funkce otevřeného typu
Chcete-li povolit funkce Open Type, nastavte vlastnost TextShaperFactory třídy LayoutOptions na instanci požadované továrny na tvarování textu. V tomto příkladu používáme HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Krok 3: Uložte dokument
Po povolení funkcí Open Type uložte dokument v požadovaném výstupním formátu, jako je PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Příklad zdrojového kódu pro funkce Open Type pomocí Aspose.Words pro .NET
Zde je úplný zdrojový kód pro použití funkcí Open Type v Aspose.Words pro .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak aktivovat a využívat funkce Open Type v Aspose.Words pro .NET. Podle podrobného průvodce a pomocí poskytnutého zdrojového kódu můžete nyní pracovat s funkcemi Open Type v dokumentech aplikace Word.

Funkce Open Type nabízejí vylepšené možnosti typografie a tvarování textu, což vám umožní vytvářet vizuálně přitažlivé a profesionálně vypadající dokumenty. Experimentujte s různými továrnami na tvarování textu a prozkoumejte možnosti funkcí Open Type ve svých projektech.

### FAQ

#### Otázka: Jak povolím funkce OpenType v Aspose.Words pro .NET?

A: Chcete-li povolit funkce OpenType v Aspose.Words pro .NET, musíte postupovat podle kroků uvedených v tutoriálu.

#### Otázka: Jaké funkce OpenType jsou podporovány v Aspose.Words pro .NET?

Odpověď: Aspose.Words for .NET podporuje několik funkcí OpenType, jako jsou ligatury, variace glyfů, kontextové substituce a další.

#### Otázka: Jak mohu zkontrolovat, zda je funkce OpenType podporována v konkrétním písmu?

Odpověď: Můžete zkontrolovat, zda je funkce OpenType podporována v konkrétním písmu pomocí`Font.OpenTypeFeatures` metoda v Aspose.Words pro .NET.

#### Otázka: Jaké další funkce formátování textu Aspose.Words for .NET podporuje?

A: Kromě funkcí OpenType podporuje Aspose.Words pro .NET také další funkce formátování textu, jako je formátování odstavců, vytváření tabulek, přidávání obrázků atd.

#### Otázka: Mohu používat funkce OpenType ve všech verzích Aspose.Words pro .NET?

A: Funkce OpenType jsou podporovány v novějších verzích Aspose.Words pro .NET. Ujistěte se, že používáte kompatibilní verzi, abyste mohli využívat tyto funkce.