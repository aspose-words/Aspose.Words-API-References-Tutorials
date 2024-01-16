---
title: Přesunout do záhlaví zápatí v dokumentu aplikace Word
linktitle: Přesunout do záhlaví zápatí v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Pomocí tohoto podrobného průvodce se dozvíte, jak používat Aspose.Words for .NET k navigaci a úpravě záhlaví a zápatí v dokumentech aplikace Word.
type: docs
weight: 10
url: /cs/net/add-content-using-documentbuilder/move-to-headers-footers/
---
V tomto příkladu prozkoumáme funkci Přesunout do záhlaví zápatí Aspose.Words pro .NET. Aspose.Words je výkonná knihovna pro manipulaci s dokumenty, která umožňuje vývojářům vytvářet, upravovat a převádět dokumenty aplikace Word programově. Funkce Přesunout do záhlaví/zápatí nám umožňuje přecházet do různých záhlaví a zápatí v dokumentu a přidávat do nich obsah.

Pojďme si projít zdrojový kód krok za krokem, abychom pochopili, jak používat funkci Přesunout do záhlaví/zápatí pomocí Aspose.Words pro .NET.

## Krok 1: Inicializace dokumentu a tvůrce dokumentů

Nejprve inicializujte objekty Document a DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Konfigurace záhlaví a zápatí

Zadejte nastavení záhlaví/zápatí dokumentu. V tomto příkladu jsme nastavili záhlaví a zápatí tak, aby se lišily pro první stránku a pro liché/sudé stránky:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Krok 3: Vytvoření záhlaví pro různé stránky

Přejděte na každý typ záhlaví a přidejte k nim obsah. V tomto příkladu vytvoříme záhlaví pro první stránku, sudé stránky a všechny ostatní stránky:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Krok 4: Vytvoření stránek v dokumentu
Přidáním obsahu do dokumentu vytvoříte více stránek. Například:

```csharp
// Vytvořte v dokumentu dvě stránky.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Krok 5: Uložení dokumentu

Uložte upravený dokument na požadované místo:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Ujistěte se, že jste zadali správnou cestu k souboru a formát (např. DOCX).

### Příklad zdrojového kódu pro Move To Headers/Footers pomocí Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Určete, že chceme záhlaví a zápatí odlišovat pro první, sudé a liché stránky.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Vytvořte záhlaví.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Vytvořte v dokumentu dvě stránky.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## Závěr

tomto příkladu jsme prozkoumali funkci Přesunout do záhlaví/zápatí Aspose.Words pro .NET. Naučili jsme se, jak přecházet do různých záhlaví a zápatí v dokumentu aplikace Word a přidávat do nich obsah pomocí třídy DocumentBuilder. Tato funkce umožňuje vývojářům přizpůsobit záhlaví a zápatí pro konkrétní stránky nebo sekce a poskytuje flexibilitu při vytváření profesionálních a strukturovaných dokumentů. Aspose.Words for .NET poskytuje výkonnou sadu nástrojů pro programovou manipulaci s dokumenty Wordu, což z něj činí základní knihovnu pro aplikace pro zpracování dokumentů.

### Nejčastější dotazy pro přesun do záhlaví a zápatí v dokumentu aplikace Word

#### Otázka: Jaký je účel funkce Přesunout do záhlaví/zápatí v Aspose.Words pro .NET?

Odpověď: Funkce Přesunout do záhlaví/zápatí v Aspose.Words for .NET umožňuje vývojářům přejít na různá záhlaví a zápatí v dokumentu aplikace Word a přidávat do nich obsah programově. Je to užitečné, když potřebujete upravit záhlaví a zápatí pro různé stránky nebo sekce v dokumentu.

#### Otázka: Mohu mít různá záhlaví a zápatí pro různé stránky v dokumentu?

Odpověď: Ano, můžete určit různá záhlaví a zápatí pro první stránku, sudé stránky a liché stránky pomocí vlastností PageSetup.DifferentFirstPageHeaderFooter a PageSetup.OddAndEvenPagesHeaderFooter.

#### Otázka: Jak mohu přidat obsah do konkrétních záhlaví a zápatí?

Odpověď: Chcete-li přidat obsah do konkrétních záhlaví a zápatí, použijte metodu MoveToHeaderFooter třídy DocumentBuilder. Na základě vašich požadavků se můžete přesunout do záhlaví HeaderFirst, HeaderEven a HeaderPrimary nebo zápatí FooterFirst, FooterEven a FooterPrimary.

#### Otázka: Mohu vytvořit záhlaví a zápatí pro konkrétní sekci v dokumentu?

Odpověď: Ano, můžete použít metodu MoveToSection třídy DocumentBuilder k přesunu do určité sekce v dokumentu a pak vytvořit záhlaví a zápatí v této sekci.

#### Otázka: Jak mohu uložit upravený dokument do souboru pomocí Aspose.Words for .NET?

Odpověď: Upravený dokument můžete uložit do požadovaného umístění a formátu pomocí metody Save třídy Document. Ujistěte se, že jste zadali správnou cestu k souboru a formát souboru (např. DOCX).