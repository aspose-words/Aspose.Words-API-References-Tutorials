---
title: Rozdělit dokument Word podle oddílů HTML
linktitle: Podle sekcí Html
second_title: Aspose.Words API pro zpracování dokumentů
description: Zjistěte, jak rozdělit dokument aplikace Word na části Html pomocí Aspose.Words for .NET s úplným příkladem kódu.
type: docs
weight: 10
url: /cs/net/split-document/by-sections-html/
---

V tomto příkladu vám ukážeme, jak rozdělit dokument aplikace Word do samostatných sekcí ve formátu HTML pomocí funkce Podle sekcí HTML aplikace Aspose.Words for .NET. Chcete-li porozumět zdrojovému kódu a vygenerovat samostatné dokumenty HTML pro každou sekci, postupujte podle následujících kroků.

## Krok 1: Načtení dokumentu

Chcete-li začít, zadejte adresář pro váš dokument a načtěte dokument do objektu Document. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Krok 2: Rozdělení dokumentu do sekcí ve formátu HTML

Nyní nastavíme možnosti uložení pro rozdělení dokumentu na sekce ve formátu HTML. Jak na to:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Příklad zdrojového kódu pro By Sections HTML pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód funkce By HTML Sections Aspose.Words for .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

Pomocí tohoto kódu budete moci rozdělit dokument aplikace Word do samostatných sekcí ve formátu HTML pomocí Aspose.Words for .NET.

Nyní můžete generovat samostatné HTML dokumenty pro každou sekci původního dokumentu.

## Závěr

V tomto tutoriálu jsme se naučili, jak rozdělit dokument aplikace Word do samostatných sekcí ve formátu HTML pomocí funkce By HTML Sections v Aspose.Words for .NET. Podle poskytnutého zdrojového kódu můžete generovat jednotlivé HTML dokumenty pro každou sekci původního dokumentu.

Rozdělení dokumentu do sekcí může být užitečné pro různé účely, jako je vytváření webových stránek, extrahování konkrétního obsahu nebo organizace informací. Aspose.Words for .NET poskytuje výkonné API, které vám umožňuje manipulovat a upravovat dokumenty Wordu podle vašich požadavků.

Neváhejte a prozkoumejte další funkce nabízené Aspose.Words pro .NET, abyste dále zlepšili své možnosti zpracování dokumentů a zlepšili svůj pracovní postup.

### Nejčastější dotazy

#### Jak mohu přizpůsobit výstupní formát HTML?

Aspose.Words for .NET poskytuje různé možnosti přizpůsobení výstupního formátu HTML. Úpravou voleb uložení můžete upravit styl, nastavení písma, rozlišení obrázku a mnoho dalších aspektů dokumentu HTML. Podrobné informace o dostupných možnostech a jejich použití naleznete v dokumentaci Aspose.Words for .NET.

#### Mohu rozdělit dokument na základě jiných kritérií?

Ano, kromě použití konců oddílů jako kritérií rozdělení nabízí Aspose.Words pro .NET další možnosti, jako jsou konce odstavců, styly nadpisů nebo specifický obsah jako kritéria pro rozdělení dokumentu. Můžete si vybrat nejvhodnější kritéria na základě vašich požadavků a podle toho upravit kód.

#### Je možné rozdělit dokument do jiných formátů než HTML?

Ano, Aspose.Words for .NET podporuje rozdělení dokumentu do různých formátů včetně PDF, prostého textu, obrázků a dalších. Můžete upravit možnosti uložení, abyste vygenerovali požadovaný výstupní formát. Další podrobnosti o dostupných formátech a o tom, jak je zadat v možnostech uložení, najdete v dokumentaci Aspose.Words for .NET.

#### Mohu rozdělit více dokumentů současně?

Ano, proces rozdělení můžete použít na více dokumentů současně tím, že projdete kolekcí dokumentů a spustíte kód rozdělení pro každý dokument samostatně. To vám umožní efektivně zpracovávat více dokumentů a generovat samostatné sekce pro každý z nich.

#### Jak mohu sloučit oddíly zpět do jednoho dokumentu?

Aspose.Words for .NET také poskytuje metody pro sloučení více dokumentů nebo sekcí zpět do jednoho dokumentu. Využitím těchto slučovacích funkcí můžete kombinovat samostatně generované sekce a vytvořit jednotný dokument. Další informace o tom, jak sloučit dokumenty nebo oddíly, najdete v dokumentaci Aspose.Words for .NET.


