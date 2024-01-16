---
title: Rozdělit dokument Word podle nadpisů Html
linktitle: Podle nadpisů Html
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce vysvětlující zdrojový kód C# dokumentu rozděleného slova podle nadpisu HTML funkce Aspose.Words for .NET
type: docs
weight: 10
url: /cs/net/split-document/by-headings-html/
---
V tomto tutoriálu vás provedeme tím, jak rozdělit dokument aplikace Word na menší části pomocí funkce By HTML Heading Aspose.Words for .NET. Chcete-li porozumět zdrojovému kódu a vygenerovat samostatné dokumenty HTML na základě nadpisu, postupujte podle následujících kroků.

## Krok 1: Načtení dokumentu

Chcete-li začít, zadejte adresář pro váš dokument a načtěte dokument do objektu Document. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Krok 2: Rozdělení dokumentu podle nadpisu ve formátu HTML

Nyní nastavíme možnosti uložení pro rozdělení dokumentu na menší části na základě nadpisu ve formátu HTML. Zde je postup:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Rozdělte dokument na menší části, v tomto případě jej oddělte podle názvu.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Příklad zdrojového kódu pro By Headings HTML pomocí Aspose.Words pro .NET

Zde je kompletní zdrojový kód pro funkci By HTML Heading Aspose.Words pro .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Rozdělte dokument na menší části, v tomto případě rozdělené podle nadpisu.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

S tímto kódem budete moci rozdělit dokument aplikace Word na menší části pomocí Aspose.Words for .NET na základě nadpisů. Pro každou část pak můžete vygenerovat samostatné HTML dokumenty.

## Závěr

 V tomto tutoriálu jsme se naučili, jak rozdělit dokument aplikace Word na menší části pomocí funkce By HTML Heading Aspose.Words for .NET. Zadáním`DocumentSplitCriteria` tak jako`HeadingParagraph` v`HtmlSaveOptions`, byli jsme schopni vygenerovat samostatné HTML dokumenty na základě nadpisů přítomných v původním dokumentu.

Rozdělení dokumentu podle nadpisů může být užitečné pro organizaci a správu obsahu, zejména ve velkých dokumentech s více oddíly. Aspose.Words for .NET poskytuje spolehlivé a efektivní řešení pro manipulaci s rozdělováním dokumentů a generování výstupu v různých formátech.

Neváhejte a prozkoumejte další funkce a možnosti poskytované Aspose.Words pro .NET, abyste dále zlepšili své možnosti zpracování dokumentů a zefektivnili svůj pracovní postup.

### Nejčastější dotazy

#### Jak mohu rozdělit dokument aplikace Word na menší části na základě nadpisů pomocí Aspose.Words for .NET?

 Chcete-li rozdělit dokument aplikace Word na základě nadpisů, můžete použít funkci Podle nadpisu HTML aplikace Aspose.Words for .NET. Postupujte podle poskytnutého zdrojového kódu a nastavte`DocumentSplitCriteria` na`HeadingParagraph` v`HtmlSaveOptions` objekt. Tím se dokument rozdělí na menší části v každém nadpisu.

#### Na jaké formáty mohu rozdělit dokument aplikace Word?

Poskytnutý zdrojový kód ukazuje rozdělení dokumentu aplikace Word na menší části ve formátu HTML. Aspose.Words for .NET však podporuje různé výstupní formáty, včetně DOCX, PDF, EPUB a dalších. Můžete upravit kód a zadat požadovaný výstupní formát v`HtmlSaveOptions` objekt podle toho.

#### Mohu zvolit jiná kritéria pro rozdělení dokumentu?

 Ano, můžete si vybrat jiná kritéria pro rozdělení dokumentu na základě vašich požadavků. Aspose.Words for .NET poskytuje několik možností kritérií, jako např`HeadingParagraph`, `Page`, `Section` , a více. Upravte`DocumentSplitCriteria` nemovitost v`HtmlSaveOptions` objektu a vyberte vhodná kritéria pro rozdělení.

#### Jak mohu přizpůsobit výstupní HTML pro rozdělené části?

 Aspose.Words for .NET vám umožňuje přizpůsobit výstupní HTML pro rozdělené části zadáním dalších možností v`HtmlSaveOptions` objekt. Můžete ovládat různé aspekty, jako jsou styly CSS, obrázky, písma a další. Další podrobnosti o přizpůsobení výstupu HTML naleznete v dokumentaci Aspose.Words.

#### Mohu rozdělit dokument na základě více kritérií?

 Ano, dokument můžete rozdělit na základě více kritérií tak, že odpovídajícím způsobem zkombinujete možnosti kritérií. Můžete například rozdělit dokument jak podle nadpisu, tak podle stránky nastavením`DocumentSplitCriteria`majetek do`HeadingParagraph | Page`. Tím se dokument rozdělí na každý nadpis a každou stránku a vytvoří menší části na základě obou kritérií.