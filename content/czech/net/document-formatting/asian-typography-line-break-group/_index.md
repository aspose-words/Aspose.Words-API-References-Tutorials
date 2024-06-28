---
title: Skupina Přerušení čáry Asijské Typografie V Dokumentu Wordu
linktitle: Skupina Přerušení čáry Asijské Typografie V Dokumentu Wordu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat skupinu zalomení řádků asijské typografie v dokumentu aplikace Word pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/document-formatting/asian-typography-line-break-group/
---
V tomto tutoriálu vám ukážeme, jak používat skupinu zalomení řádků asijské typografie ve funkci dokumentu aplikace Word s Aspose.Words pro .NET. Chcete-li porozumět zdrojovému kódu a použít změny formátování, postupujte podle následujících kroků.

## Krok 1: Načtení dokumentu

Chcete-li začít, zadejte adresář pro vaše dokumenty a načtěte dokument obsahující asijskou typografii do objektu Document. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Krok 2: Nastavení asijské typografie

Nyní nakonfigurujeme nastavení asijské typografie pro první odstavec dokumentu. Zde je postup:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Krok 3: Uložení dokumentu

 Po vložení pole formuláře pro zadání textu uložte dokument na požadované místo pomocí`Save` metoda. Ujistěte se, že jste zadali správnou cestu k souboru:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Příklad zdrojového kódu pro asijské typografie Line Break Group pomocí Aspose.Words pro .NET

Zde je kompletní zdrojový kód pro funkci Aspose.Words pro .NET asijské typografie Line Break Group:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
S tímto kódem budete moci použít skupinu zalomení řádků asijské typografie pomocí Aspose.Words for .NET.

## Závěr

 V tomto tutoriálu jsme prozkoumali funkci "Asian Typography Line Break Group" v Aspose.Words pro .NET. Nakonfigurováním`FarEastLineBreakControl`, `WordWrap` , a`HangingPunctuation` vlastnosti`ParagraphFormat`jsme byli schopni ovládat chování zalamování řádků pro asijskou typografii v dokumentu aplikace Word. Tato funkce je užitečná pro práci s asijskými znaky a pro zajištění správného zalomení řádků a zalamování slov v dokumentech se smíšeným jazykovým obsahem.

### FAQ

#### Otázka: Co je funkce "Asian Typography Line Break Group" v Aspose.Words for .NET?

Odpověď: Funkce "Skupina zalamování řádků asijské typografie" v Aspose.Words pro .NET vám umožňuje ovládat chování zalamování řádků pro asijskou typografii v dokumentu aplikace Word. Konkrétně ovlivňuje způsob přerušování a zalamování řádků při práci s asijskými znaky v odstavcích.

#### Otázka: Jak povolím v Aspose.Words for .NET "Skupinu přerušení čáry asijské typografie"?

 A: Chcete-li povolit "Skupinu přerušení čáry asijské typografie", musíte nakonfigurovat`FarEastLineBreakControl`, `WordWrap` , a`HangingPunctuation` vlastnosti`ParagraphFormat` pro příslušné odstavce ve vašem dokumentu. Nastavení`FarEastLineBreakControl` na`false` zajišťuje, že se s asijskými znaky zachází podobně jako se znaky latinky, pokud jde o zalamování řádků.`WordWrap` nastaven na`true` umožňuje zalamování slov pro asijskou typografii a`HangingPunctuation` nastaven na`false` zabraňuje vinutí interpunkce v asijském textu.

#### Otázka: Mohu použít "Skupinu přerušení čáry asijské typografie" na konkrétní odstavce v dokumentu?

Odpověď: Ano, nastavení "Skupina přerušení řádků asijské typografie" můžete použít na konkrétní odstavce v dokumentu aplikace Word. V příkladu kódu se nastavení použijí na první odstavec dokumentu. Můžete upravit kód tak, aby cílil na další odstavce podle potřeby tím, že k nim přistoupíte prostřednictvím`Paragraphs` sbírka příslušných oddílů v dokumentu.