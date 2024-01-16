---
title: Načíst slovník dělení slov pro jazyk
linktitle: Načíst slovník dělení slov pro jazyk
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak načíst slovník dělení pro konkrétní jazyk v Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

V tomto podrobném tutoriálu vám ukážeme, jak načíst slovník dělení slov pro konkrétní jazyk do Aspose.Words pro .NET. Vysvětlíme vám poskytnutý zdrojový kód C# a ukážeme vám, jak jej implementovat do vašich vlastních projektů.

 Chcete-li začít, ujistěte se, že máte Aspose.Words for .NET nainstalovaný a nakonfigurovaný ve svém vývojovém prostředí. Pokud jste tak ještě neučinili, stáhněte si a nainstalujte knihovnu z[Aspose.Releases]https://releases.aspose.com/words/net/.

## Krok 1: Načtení dokumentu

Nejprve načtěte dokument ze zadaného adresáře:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Krok 2: Načtení slovníku dělení slov

Dále otevřete proud do souboru slovníku dělení slov a uložte jej pro požadovaný jazyk. V tomto příkladu načteme slovník pro švýcarskou němčinu (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Ujistěte se, že máte ve svém datovém adresáři příslušný soubor slovníku.

## Krok 3: Uložte upravený dokument

Nakonec upravený dokument uložte:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Tak ! Úspěšně jste načetli slovník dělení slov pro konkrétní jazyk v Aspose.Words pro .NET.

### Příklad zdrojového kódu pro načítání slovníku dělení slov pro jazyk používající Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Neváhejte použít tento kód ve svých vlastních projektech a upravit jej tak, aby vyhovoval vašim konkrétním potřebám.

### FAQ

#### Otázka: Jak načíst slovník slabik pro konkrétní jazyk v Aspose.Words?

 A: Chcete-li načíst slovník slabik pro konkrétní jazyk v Aspose.Words, můžete použít`Hyphenation` třída a`LoadDictionary()` metoda. Vytvořte instanci souboru`Hyphenation` třídy a zavolejte`LoadDictionary()` metoda určující cestu k souboru sylabizačního slovníku pro požadovaný jazyk. Tím se načte slabikářský slovník do Aspose.Words.

#### Otázka: Kde najdu soubory slabikačního slovníku pro různé jazyky?

Odpověď: Soubory slovníků slabikářů pro různé jazyky můžete najít na různých online zdrojích. Tyto soubory jsou obvykle ve formátu XML nebo TEX. Na webech věnovaných lingvistickým projektům nebo na úložištích zdrojového kódu můžete najít open source slabikářské slovníky pro různé jazyky.

#### Otázka: Jak mohu použít načtený slabičný slovník na dokument v Aspose.Words?

 Odpověď: Chcete-li použít načtený slovník slabikáře na dokument v Aspose.Words, musíte iterovat slova v dokumentu a použít`Hyphenate()` metoda`Hyphenation`třídy, abyste získali slabiku slov. Slabiková slova pak můžete formátovat podle potřeby, například přidáním pomlček mezi slabiky.

#### Otázka: Jaké jazyky jsou podporovány pro slabikování v Aspose.Words?

Odpověď: Aspose.Words podporuje slabikování pro více jazyků včetně angličtiny, francouzštiny, španělštiny, němčiny, italštiny, holandštiny, ruštiny, portugalštiny, švédštiny, norštiny, dánštiny, finštiny, polštiny, češtiny a mnoha dalších. Úplný seznam podporovaných jazyků pro slabikování najdete v dokumentaci Aspose.Words.