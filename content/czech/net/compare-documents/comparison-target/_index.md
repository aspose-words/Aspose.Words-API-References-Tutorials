---
title: Srovnání Cíl V dokumentu Word
linktitle: Srovnání Cíl V dokumentu Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se funkci porovnat cíl ve wordovém dokumentu Aspose.Words for .NET, která vám umožní porovnávat dokumenty a generovat nový dokument obsahující provedené změny.
type: docs
weight: 10
url: /cs/net/compare-documents/comparison-target/
---
Zde je podrobný průvodce vysvětlující zdrojový kód C# níže, který používá cíl porovnání ve funkci dokumentu aplikace Word Aspose.Words for .NET.

## Krok 1: Úvod

Funkce porovnání cíle Aspose.Words for .NET umožňuje porovnat dva dokumenty a vygenerovat nový dokument obsahující změny provedené v cílovém dokumentu. To může být užitečné pro sledování změn provedených mezi různými verzemi dokumentu.

## Krok 2: Nastavení prostředí

Než začnete, musíte své vývojové prostředí nastavit tak, aby fungovalo s Aspose.Words for .NET. Ujistěte se, že máte nainstalovanou knihovnu Aspose.Words a že máte vhodný projekt C# pro vložení kódu.

## Krok 3: Přidejte požadovaná sestavení

Chcete-li použít funkci cíle porovnání Aspose.Words for .NET, musíte do projektu přidat potřebná sestavení. Ujistěte se, že máte ve svém projektu správné odkazy na Aspose.Words.

```csharp
using Aspose.Words;
```

## Krok 4: Inicializace dokumentu

V tomto kroku inicializujeme dva dokumenty pro porovnání. Musíte zadat cestu k adresáři, kde jsou umístěny vaše dokumenty, a také název zdrojového dokumentu.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Inicializace dokumentu A k porovnání.
Document docA = new Document(dataDir + "DocumentA.docx");

// Klonujte dokument A, abyste vytvořili identickou kopii dokumentu B.
Document docB = docA.Clone();
```

## Krok 5: Konfigurace možností porovnání

V tomto kroku nakonfigurujeme možnosti porovnání, abychom specifikovali chování porovnání. Možnosti zahrnují možnost ignorovat formátování a také cíl porovnání, což je možnost "Zobrazit změny v" v dialogovém okně "Porovnat dokumenty" aplikace Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Krok 6: Porovnání dokumentů

Nyní dokumenty porovnáme a výsledek vygenerujeme v novém dokumentu.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 The`Compare`metoda porovná dokument A s dokumentem B a uloží změny do dokumentu A. Pro referenci můžete zadat uživatelské jméno a datum porovnání.

### Ukázkový zdrojový kód pro Comparison Target pomocí Aspose.Words pro .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Týká se možnosti "Zobrazit změny v" aplikace Microsoft Word v dialogovém okně "Porovnat dokumenty".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Závěr

V tomto článku jsme prozkoumali funkci cíle rozdílu v Aspose.Words pro .NET. Tato funkce umožňuje porovnat dva dokumenty a vygenerovat nový dokument obsahující provedené změny. Tyto znalosti můžete použít ke sledování změn mezi různými verzemi vašich dokumentů.

### FAQ

#### Otázka: Jaký je účel použití Comparison Target v Aspose.Words for .NET?

A: Comparison Target v Aspose.Words for .NET umožňuje porovnat dva dokumenty a vygenerovat nový dokument obsahující změny provedené v cílovém dokumentu. Tato funkce je užitečná pro sledování změn provedených mezi různými verzemi dokumentu a vizualizaci rozdílů v samostatném dokumentu.

#### Otázka: Jak mohu použít Comparison Target v Aspose.Words for .NET?

A: Chcete-li použít Comparison Target v Aspose.Words pro .NET, postupujte takto:
1. Nastavte své vývojové prostředí pomocí knihovny Aspose.Words.
2. Přidejte potřebné sestavy do svého projektu odkazem na Aspose.Words.
3.  Inicializujte dokumenty, které chcete porovnat, pomocí`Document` třídy nebo`DocumentBuilder` třída.
4.  Nakonfigurujte možnosti porovnání vytvořením a`CompareOptions` vlastnosti objektu a nastavení jako např`IgnoreFormatting` a`Target` (např,`ComparisonTargetType.New` pro cíl srovnání).
5.  Použijte`Compare` metoda na jednom dokumentu, předání druhého dokumentu a`CompareOptions` objekt jako parametry. Tato metoda porovná dokumenty a uloží změny v prvním dokumentu.

####  Otázka: Jaký je účel`Target` property in the `CompareOptions` class?

 A:`Target` nemovitost v`CompareOptions` třída umožňuje zadat cíl porovnání, který je podobný možnosti "Zobrazit změny v" v dialogovém okně "Porovnat dokumenty" aplikace Microsoft Word. Cíl lze nastavit na`ComparisonTargetType.New` zobrazit změny v novém dokumentu,`ComparisonTargetType.Current` zobrazit změny v aktuálním dokumentu, popř`ComparisonTargetType.Formatting` zobrazit pouze změny formátování.