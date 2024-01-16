---
title: Vytvořit záhlaví zápatí
linktitle: Vytvořit záhlaví zápatí
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vytvářet záhlaví a zápatí v dokumentech aplikace Word pomocí Aspose.Words for .NET. Upravte záhlaví a zápatí pro každou stránku.
type: docs
weight: 10
url: /cs/net/working-with-headers-and-footers/create-header-footer/
---

Zde je podrobný průvodce, který vysvětluje následující zdrojový kód C# pro vytváření záhlaví a zápatí pomocí funkce Aspose.Words for .NET. Před použitím tohoto kódu se ujistěte, že jste do projektu zahrnuli knihovnu Aspose.Words.

## Krok 1: Nastavte cestu k adresáři dokumentu

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů, kam se upravený dokument uloží.

## Krok 2: Vytvořte dokument a generátor dokumentů

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Zde vytvoříme instanci`Document` třída a instance třídy`DocumentBuilder` třída, která nám umožní manipulovat s dokumentem a přidávat prvky.

## Krok 3: Nastavte parametry stránky a první záhlaví

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Určete, zda chceme, aby se záhlaví/zápatí první stránky lišilo od ostatních stránek.
// K určení můžete také použít vlastnost PageSetup.OddAndEvenPagesHeaderFooter
// různá záhlaví/zápatí pro liché a sudé stránky.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Nastavíme parametry stránky včetně vzdálenosti záhlaví a poté se přesuneme do hlavního záhlaví (`HeaderPrimary`). K přidání textu a formátování záhlaví používáme generátor dokumentů.

## Krok 4: Vložte obrázek a text do hlavního záhlaví

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Pomocí generátoru dokumentů vložíme obrázek do levého horního rohu hlavního záhlaví, poté přidáme nějaký text zarovnaný doprava.

## Krok 5: Vložte tabulku do hlavního zápatí

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## Krok 6: Přidejte novou stránku a nastavte záhlaví/zápatí

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Tato sekce nepotřebuje jiné záhlaví/zápatí pro první stránku, potřebujeme pouze jednu titulní stránku v dokumentu,
// záhlaví/zápatí pro tuto stránku již bylo definováno v předchozí části.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Tato sekce standardně zobrazuje záhlaví/zápatí předchozí sekce, pro přerušení tohoto odkazu zavolejte currentSection.HeadersFooters.LinkToPrevious(false),
// šířka stránky je pro novou sekci jiná, takže pro tabulku zápatí musíme nastavit různé šířky buněk.
currentSection.HeadersFooters.LinkToPrevious(false);

// Pokud chceme pro tuto sekci použít již existující záhlaví/zápatí,
//ale s pár drobnými změnami by mohlo mít smysl zkopírovat záhlaví/zápatí
// z předchozí části a aplikovat potřebné změny tam, kde je chceme.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Uložte dokument
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Přidáme konec stránky a konec sekce, abychom vytvořili novou stránku, kde budou viditelné primární záhlaví/zápatí. Nastavíme parametry pro novou sekci, pak použijeme`CopyHeadersFootersFromPreviousSection` metoda pro zkopírování záhlaví/zápatí z předchozí části. Nakonec nastavíme vhodné šířky buněk pro hlavní tabulku zápatí a dokument uložíme.

### Příklad zdrojového kódu pro vytvoření záhlaví a zápatí pomocí Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Určete, zda chceme, aby se záhlaví/zápatí první stránky lišilo od ostatních stránek.
// K určení můžete také použít vlastnost PageSetup.OddAndEvenPagesHeaderFooter
// různá záhlaví/zápatí pro liché a sudé stránky.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Vložte umístěný obrázek do horního/levého rohu záhlaví.
// Vzdálenost od horního/levého okraje stránky je nastavena na 10 bodů.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Tabulkou se dvěma buňkami uděláme jednu část textu na řádku (s číslováním stránek).
// Zarovnat doleva a druhou část textu (s autorským právem) zarovnat doprava.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// K automatickému výpočtu aktuálního čísla stránky a mnoha stránek používá pole PAGE a NUMPAGES.
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();

// Zalomením stránky vytvoříte druhou stránku, na které budou vidět primární záhlaví/zápatí.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Tato sekce nepotřebuje jiné záhlaví/zápatí na první stránce, potřebujeme pouze jednu titulní stránku v dokumentu,
// záhlaví/zápatí pro tuto stránku již bylo definováno v předchozí části.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Tato sekce zobrazuje záhlaví/zápatí z předchozí sekce
// ve výchozím nastavení zavolejte currentSection.HeadersFooters.LinkToPrevious(false) pro zrušení této šířky stránky
// je pro novou sekci odlišná, a proto musíme pro tabulku zápatí nastavit různé šířky buněk.
currentSection.HeadersFooters.LinkToPrevious(false);

// Pokud chceme pro tuto sekci použít již existující sadu záhlaví/zápatí.
// Ale s některými drobnými úpravami může být účelné zkopírovat záhlaví/zápatí
// z předchozí části a aplikujte potřebné úpravy tam, kde je chceme.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### FAQ

#### Otázka: Jak mohu přidat záhlaví do svého dokumentu v Aspose.Words?

 A: Chcete-li přidat záhlaví do dokumentu v Aspose.Words, můžete použít`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` metoda. Tato metoda přidá primární nadpis do první části vašeho dokumentu.

#### Otázka: Jak mohu přidat zápatí do svého dokumentu v Aspose.Words?

 A: Chcete-li přidat zápatí do dokumentu v Aspose.Words, můžete použít`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`metoda. Tato metoda přidá primární zápatí do první části dokumentu.

#### Otázka: Jak mohu přidat text do záhlaví nebo zápatí v Aspose.Words?

 A: Chcete-li přidat text do záhlaví nebo zápatí v Aspose.Words, můžete použít`HeaderFooter.Paragraphs` vlastnost, abyste získali kolekci odstavců záhlaví nebo zápatí, pak přidejte odstavec obsahující váš text do této kolekce pomocí`ParagraphCollection.Add` metoda.

#### Otázka: Mohu upravit obsah záhlaví nebo zápatí pomocí obrázků a čísel stránek v Aspose.Words?

 Odpověď: Ano, obsah záhlaví nebo zápatí můžete upravit pomocí obrázků a čísel stránek v Aspose.Words. Můžete použít předměty jako`Shape` přidat obrázky a objekty jako`Field` přidat čísla stránek do záhlaví nebo zápatí.

#### Otázka: Mohu změnit písmo, velikost a barvu textu v záhlaví nebo zápatí v Aspose.Words?

 Odpověď: Ano, můžete změnit písmo, velikost a barvu textu v záhlaví nebo zápatí v Aspose.Words. Můžete přistupovat k vlastnostem formátování textu, jako je např`Font` změnit písmo,`Size` upravit velikost a`Color`pro nastavení barvy textu.