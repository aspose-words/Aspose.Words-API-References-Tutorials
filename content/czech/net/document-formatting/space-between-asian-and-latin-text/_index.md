---
title: Prostor mezi asijským a latinským textem v dokumentu aplikace Word
linktitle: Prostor mezi asijským a latinským textem v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak automaticky upravit mezeru mezi asijským a latinským textem v dokumentu aplikace Word pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/document-formatting/space-between-asian-and-latin-text/
---
V tomto tutoriálu vám ukážeme, jak používat funkci Mezerník mezi asijským a latinským textem ve funkci dokumentu aplikace Word s Aspose.Words pro .NET. Chcete-li porozumět zdrojovému kódu a použít změny, postupujte podle následujících kroků.

## Krok 1: Vytvoření a konfigurace dokumentu

Chcete-li začít, vytvořte nový dokument a přidružený objekt DocumentBuilder. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Nastavení mezery mezi asijským a latinským textem

Nyní nakonfigurujeme mezeru mezi asijským a latinským textem pomocí vlastností objektu CharacterFormat. Zde je postup:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Krok 3: Uložení dokumentu

 Po vložení pole formuláře pro zadání textu uložte dokument na požadované místo pomocí`Save` metoda. Ujistěte se, že jste zadali správnou cestu k souboru:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Příklad zdrojového kódu pro prostor mezi asijským a latinským textem pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód funkce Space Between Asian and Latin Text s Aspose.Words for .NET:


```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

S tímto kódem budete moci automaticky upravit mezeru mezi asijským a latinským textem ve vašem dokumentu pomocí Aspose.Words for .NET.

## Závěr

V tomto tutoriálu jsme prozkoumali proces použití funkce Space k úpravě mezer mezi asijským a latinským textem v dokumentu aplikace Word pomocí Aspose.Words for .NET. Dodržováním nastíněných kroků můžete zajistit správné mezery a zarovnání, což je užitečné zejména při práci se smíšeným asijským a latinským obsahem.

### FAQ

#### Otázka: Jaká je funkce mezera mezi asijským a latinským textem v dokumentu aplikace Word?

Odpověď: Funkce mezery mezi asijským a latinským textem v dokumentu aplikace Word odkazuje na schopnost automaticky upravit mezery mezi textem napsaným v různých písmech, jako je asijské (např. čínština, japonština) a latinka (např. angličtina).

#### Otázka: Proč je úprava mezery mezi asijským a latinským textem důležitá?

Odpověď: Úprava mezery mezi asijským a latinským textem je zásadní, aby se zajistilo, že různá písma se v dokumentu harmonicky prolínají. Správné řádkování zlepšuje čitelnost a celkový vizuální vzhled a zabraňuje tomu, aby text vypadal příliš stísněně nebo roztaženě.

#### Otázka: Mohu přizpůsobit úpravy prostoru mezi různými skripty?

 Odpověď: Ano, můžete upravit úpravy prostoru mezi různými skripty pomocí`AddSpaceBetweenFarEastAndAlpha` a`AddSpaceBetweenFarEastAndDigit` vlastnosti. Povolením nebo zakázáním těchto vlastností můžete ovládat mezeru mezi asijským a latinským textem a také mezi asijským textem a čísly.

#### Otázka: Podporuje Aspose.Words for .NET další funkce formátování dokumentů?

Odpověď: Ano, Aspose.Words for .NET nabízí rozsáhlou podporu pro různé funkce formátování dokumentů. Obsahuje funkce pro styly písem, odstavce, tabulky, obrázky a další. S dokumenty Wordu můžete efektivně manipulovat a programově je formátovat.

#### Otázka: Kde najdu další zdroje a dokumentaci pro Aspose.Words pro .NET?

 Odpověď: Komplexní zdroje a dokumentaci o používání Aspose.Words pro .NET naleznete na adrese[Aspose.Words API Reference](https://reference.aspose.com/words/net/). Najdete zde podrobné průvodce, návody, příklady kódu a odkazy na API, které vám pomohou efektivně využívat výkonné funkce Aspose.Words pro .NET.