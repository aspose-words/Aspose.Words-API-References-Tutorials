---
title: Horizontální pravidlo
linktitle: Horizontální pravidlo
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vložit vodorovné pravidlo pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/horizontal-rule/
---

V tomto příkladu vám ukážeme, jak používat funkci vodorovného pravítka s Aspose.Words pro .NET. Horizontální pravidlo se používá k vizuálnímu oddělení částí dokumentu.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Vložení vodorovného pravítka

 Vodorovné pravítko můžeme vložit pomocí`InsertHorizontalRule` metoda generátoru dokumentů.

```csharp
builder. InsertHorizontalRule();
```

## Ukázkový zdrojový kód pro horizontální pravidlo s Aspose.Words pro .NET

```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

// Vložte vodorovné pravítko.
builder.InsertHorizontalRule();
```

gratuluji! Nyní jste se naučili používat funkci vodorovného pravítka s Aspose.Words pro .NET.


### FAQ

#### Otázka: Jak v Markdown vytvořím vodorovné pravítko?

Odpověď: Chcete-li vytvořit vodorovné pravítko v Markdown, můžete na prázdném řádku použít jeden z následujících symbolů: tři hvězdičky (\***), tři čárky (\---), nebo tři podtržítka (\___).

#### Otázka: Mohu upravit vzhled vodorovného pravítka v Markdown?

Odpověď: Ve standardním Markdown neexistuje způsob, jak upravit vzhled vodorovných pravítek. Některé pokročilé editory a rozšíření Markdown však nabízejí další funkce přizpůsobení.

#### Otázka: Podporují horizontální pravítka všechny editory Markdown?

Odpověď: Ano, většina populárních editorů Markdown podporuje horizontální pravítka. Vždy je však nejlepší zkontrolovat dokumentaci konkrétního dodavatele, abyste se ujistili, že je podporována.

#### Otázka: Jaké další prvky mohu vytvořit v Markdown?

Odpověď: Kromě vodorovných pravítek můžete v Markdown vytvářet nadpisy, odstavce, seznamy, odkazy, obrázky, tabulky a další.