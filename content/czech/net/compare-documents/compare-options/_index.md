---
title: Porovnat možnosti v dokumentu aplikace Word
linktitle: Porovnat možnosti v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce vysvětlující zdrojový kód C# možností porovnání ve funkci dokumentu aplikace Word s Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/compare-documents/compare-options/
---
V tomto tutoriálu vysvětlíme, jak používat možnosti porovnání v dokumentu aplikace Word s Aspose.Words pro .NET. Chcete-li porozumět zdrojovému kódu a použít změny, postupujte podle následujících kroků.

## Krok 1: Porovnejte dokumenty s vlastními možnostmi

 Chcete-li začít, načtěte dva dokumenty k porovnání. V tomto příkladu použijeme`Clone()` způsob vytvoření kopie původního dokumentu. Zde je postup:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Krok 2: Konfigurace možností porovnání

 Nyní nakonfigurujeme možnosti porovnání vytvořením a`CompareOptions` objekt a nastavení různých vlastností podle potřeby. Zde je postup:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Krok 3: Porovnejte dokumenty s vlastními možnostmi

 Nyní použijeme`Compare()` metoda předávání vlastních možností pro porovnání dvou dokumentů. Tato metoda označí změny v původním dokumentu. Zde je postup:

```csharp
// Porovnejte dokumenty s vlastními možnostmi
docA.Compare(docB, "user", DateTime.Now, options);

// Zkontrolujte, zda jsou dokumenty stejné
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Příklad zdrojového kódu pro možnosti porovnání pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód funkce Porovnat možnosti s Aspose.Words pro .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

S tímto kódem můžete porovnat dva dokumenty pomocí vlastních možností ignorovat specifické prvky při porovnávání s Aspose.Words pro .NET.

## Závěr

tomto tutoriálu jsme se naučili, jak používat možnosti porovnání v Aspose.Words pro .NET k přizpůsobení procesu porovnání při porovnávání dvou dokumentů. Zadáním různých možností můžete ignorovat konkrétní prvky a učinit proces porovnávání flexibilnějším. Tato funkce vám umožňuje mít větší kontrolu nad procesem porovnání a přizpůsobit jej vašim konkrétním požadavkům. Aspose.Words for .NET poskytuje výkonné možnosti porovnávání dokumentů, což usnadňuje identifikaci rozdílů mezi dokumenty, přičemž podle potřeby ignoruje určité prvky.

### FAQ

#### Otázka: Jaký je účel použití Možnosti porovnání v Aspose.Words pro .NET?

Odpověď: Možnosti porovnání v Aspose.Words pro .NET vám umožňují přizpůsobit proces porovnání při porovnávání dvou dokumentů. Pomocí těchto voleb můžete určit, které prvky se mají během porovnávání ignorovat, jako jsou změny formátování, záhlaví a zápatí, tabulky, pole, komentáře, textová pole a poznámky pod čarou.

#### Otázka: Jak mohu použít možnosti porovnání v Aspose.Words pro .NET?

A: Chcete-li použít možnosti porovnání v Aspose.Words pro .NET, postupujte takto:
1. Vložte dva dokumenty, které chcete porovnat, do samostatných objektů dokumentu.
2.  Použijte`Clone()` způsob vytvoření kopie původního dokumentu.
3.  Vytvořit`CompareOptions` objekt a nastavte jeho vlastnosti pro přizpůsobení procesu porovnávání. Můžete určit, které prvky se mají během porovnávání ignorovat.
4.  Použijte`Compare()` metoda na jednom z dokumentů a předat druhý dokument a`CompareOptions` objekt jako parametry. Tato metoda porovná dokumenty na základě zadaných možností a označí změny v původním dokumentu.
5.  Zkontrolovat`Revisions` vlastnost původního dokumentu. Pokud je počet nula, znamená to, že dokumenty jsou s ohledem na zadané možnosti totožné.

#### Otázka: Jaké jsou běžné možnosti dostupné v CompareOptions?

Odpověď: Mezi běžné možnosti dostupné v CompareOptions patří:
- `IgnoreFormatting`: Ignoruje změny ve formátování.
- `IgnoreHeadersAndFooters`: Ignoruje změny v záhlaví a zápatí.
- `IgnoreCaseChanges`: Ignoruje změny velkých a malých písmen (velká/malá písmena).
- `IgnoreTables`: Ignoruje změny v tabulkách.
- `IgnoreFields`: Ignoruje změny v polích.
- `IgnoreComments`: Ignoruje změny v komentářích.
- `IgnoreTextboxes`Ignoruje změny v textových polích.
- `IgnoreFootnotes`: Ignoruje změny v poznámkách pod čarou.

#### Otázka: Mohu použít vlastní možnosti pro konkrétní prvky během porovnávání dokumentů?

 Odpověď: Ano, během porovnávání dokumentů můžete použít vlastní volby pro konkrétní prvky. Nastavením vlastností`CompareOptions` podle toho si můžete vybrat, které prvky ignorovat a které vzít v úvahu při porovnávání.