---
title: Optimalizujte velikost PDF pomocí přeskočení vložených písem Arial & Times Roman
linktitle: Optimalizujte velikost PDF pomocí přeskočení vložených písem Arial & Times Roman
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce generováním optimalizovaného PDF bez vkládání písem Arial a Times Roman pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Tento článek poskytuje podrobného průvodce, jak používat funkci k optimalizaci velikosti PDF přeskočením vložených písem Arial a Times Roman na velikost metasouboru pomocí Aspose.Words for .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto kurzu budete schopni porozumět tomu, jak nakonfigurovat možnost režimu vkládání písem v dokumentu a generovat PDF bez vkládání písem Arial a Times Roman.

Než začnete, ujistěte se, že jste ve svém projektu nainstalovali a nakonfigurovali knihovnu Aspose.Words for .NET. Knihovnu a pokyny k instalaci najdete na webu Aspose.

## Krok 1: Definujte adresář dokumentů

 Chcete-li začít, musíte definovat cestu k adresáři, kde jsou umístěny vaše dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Nahrajte dokument

Dále musíme načíst dokument, který chceme zpracovat. V tomto příkladu předpokládáme, že dokument se nazývá "Rendering.docx" a je umístěn v určeném adresáři dokumentů.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Krok 3: Nakonfigurujte možnosti uložení jako PDF s vložením písem

 Chcete-li přeskočit vkládání písem Arial a Times Roman do vygenerovaného PDF, musíme nakonfigurovat`PdfSaveOptions` objekt a nastavte`FontEmbeddingMode`majetek do`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Krok 4: Uložte dokument jako PDF bez vložených písem

Nakonec můžeme dokument uložit ve formátu PDF pomocí dříve nakonfigurovaných možností uložení.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

To je vše ! Úspěšně jste vygenerovali PDF bez vložení písem Arial a Times Roman pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro přeskočení vložených písem Arial a Times Roman ve velikosti metasouboru pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Závěr

tomto tutoriálu jsme vysvětlili, jak zakázat vkládání písem Arial a Times Roman do dokumentu PDF pomocí Aspose.Words for .NET. Podle uvedených kroků můžete vygenerovat soubor PDF bez vkládání těchto specifických písem, což může pomoci snížit velikost souboru a zajistit lepší kompatibilitu dokumentů na různých platformách. Při používání této funkce nezapomeňte zvážit důsledky zakázání vkládání písem. Neváhejte a prozkoumejte další funkce Aspose.Words for .NET pro optimalizaci generování vašich souborů PDF.

### Často kladené otázky

#### Otázka: Co zakazuje vkládání písem Arial a Times Roman do dokumentu PDF a proč je to důležité?
Odpověď: Zakázání vkládání písem Arial a Times Roman do dokumentu PDF znamená, že tato písma nejsou zahrnuta do vygenerovaného souboru PDF. To může být důležité pro zmenšení velikosti souboru PDF tím, že se vyhnete zahrnutí písem, která jsou již běžně dostupná v systémech pro čtení PDF. Může také pomoci zajistit lepší kompatibilitu a konzistentní vzhled dokumentu PDF na různých zařízeních a platformách.

#### Otázka: Jak mohu nakonfigurovat Aspose.Words pro .NET, aby do dokumentu PDF nevkládala písma Arial a Times Roman?
Odpověď: Chcete-li nakonfigurovat Aspose.Words pro .NET tak, aby do dokumentu PDF nevkládala písma Arial a Times Roman, postupujte takto:

 Nahrazením nastavte cestu k adresáři, kde jsou umístěny vaše dokumenty`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

 Vložte dokument, který chcete zpracovat, pomocí`Document` třída a zadaná cesta dokumentu.

 Vytvořte instanci souboru`PdfSaveOptions` třídu a nastavte`FontEmbeddingMode`majetek do`PdfFontEmbeddingMode.EmbedAll`. Tím se do vygenerovaného souboru PDF vloží všechna písma kromě Arial a Times Roman.

 Použijte`Save` metoda`Document` objekt k uložení dokumentu ve formátu PDF s uvedením dříve nakonfigurovaných možností uložení.

#### Otázka: Jaké jsou výhody deaktivace vkládání písem Arial a Times Roman do dokumentu PDF?
Odpověď: Výhody deaktivace vkládání písem Arial a Times Roman do dokumentu PDF jsou:

Zmenšení velikosti souboru PDF: Zabráněním vkládání běžně dostupných písem, jako jsou Arial a Times Roman, lze velikost souboru PDF zmenšit, což usnadňuje ukládání, sdílení a přenos souborů.

Lepší kompatibilita: Použitím písem, která jsou běžně dostupná v systémech pro čtení PDF, zajistíte lepší kompatibilitu a vzhled dokumentu na různých zařízeních a platformách.

#### Otázka: Jaké jsou důsledky zakázání vkládání písem Arial a Times Roman do dokumentu PDF?
Odpověď: Zakázání vkládání písem Arial a Times Roman do dokumentu PDF má následující důsledky:

Odlišný vzhled: Pokud v systému, kde je PDF otevřen, nejsou k dispozici písma Arial a Times Roman, použijí se náhradní písma, což může vést k jinému vzhledu, než bylo zamýšleno.

Problémy s čitelností: Použité náhradní písma nemusí být tak čitelné jako původní písma, což může ovlivnit čitelnost dokumentu.