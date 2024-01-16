---
title: Zmenšete velikost PDF pomocí změny velikosti písem WMF na velikost metasouboru
linktitle: Zmenšete velikost PDF pomocí změny velikosti písem WMF na velikost metasouboru
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce pro zmenšení velikosti PDF pomocí měřítka wmf písem na velikost metasouboru při převodu do PDF pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Tento článek poskytuje podrobný návod, jak zmenšit velikost PDF pomocí funkce měřítka wmf písem na velikost metasouboru pomocí Aspose.Words pro .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto tutoriálu budete schopni porozumět tomu, jak povolit nebo zakázat změnu velikosti písma WMF při převodu do PDF.

Než začnete, ujistěte se, že jste ve svém projektu nainstalovali a nakonfigurovali knihovnu Aspose.Words for .NET. Knihovnu a pokyny k instalaci najdete na webu Aspose.

## Krok 1: Definujte adresář dokumentů

 Chcete-li začít, musíte definovat cestu k adresáři, kde jsou umístěny vaše dokumenty. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Nahrajte dokument

Dále musíme načíst dokument, který chceme zpracovat. V tomto příkladu předpokládáme, že dokument se nazývá "WMF s textem.docx" a je umístěn v zadaném adresáři dokumentů.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Krok 3: Nakonfigurujte možnosti vykreslování metasouboru

 Chcete-li povolit nebo zakázat změnu velikosti písma WMF na velikost metasouboru, musíme nakonfigurovat`MetafileRenderingOptions`objekt. V tomto příkladu zakážeme změnu velikosti písma nastavením`ScaleWmfFontsToMetafileSize`majetek do`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Krok 4: Nakonfigurujte možnosti uložení jako PDF s možnostmi vykreslování metasouborů

Nakonec můžeme nakonfigurovat možnosti ukládání do PDF pomocí možností vykreslování metasouborů nakonfigurovaných dříve.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Krok 5: Uložte dokument jako PDF s možnostmi vykreslování metasouborů

Uložte dokument ve formátu PDF pomocí dříve nakonfigurovaných možností uložení.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

To je vše ! Úspěšně jste povolili nebo zakázali změnu velikosti písma WMF na velikost metasouboru při převodu

dokument PDF pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro změnu velikosti písem WMF na velikost metasouboru pomocí Aspose.Words for .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Pokud Aspose.Words nemůže správně vykreslit některé záznamy metasouboru do vektorové grafiky
	// pak Aspose.Words vykreslí tento metasoubor do bitmapy.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Závěr

tomto tutoriálu jsme vysvětlili, jak povolit nebo zakázat změnu velikosti písem WMF na velikost metasouboru v dokumentu PDF pomocí Aspose.Words for .NET. Podle popsaných kroků můžete snadno určit, zda má být velikost písem WMF při převodu do dokumentu PDF změněna tak, aby odpovídala velikosti metasouboru. To vám může pomoci zmenšit velikost generovaného souboru PDF a zlepšit výkon vykreslování. Ujistěte se, že jste zadali správnou cestu k vašim dokumentům a podle potřeby nakonfigurujte možnosti vykreslování metasouborů.

### Často kladené otázky

#### Otázka: Co je změna velikosti písem WMF na velikost metasouboru v dokumentu PDF?
Odpověď: Změna velikosti písem WMF na velikost metasouboru v dokumentu PDF je funkce, která řídí, zda má být písmo WMF při převodu na dokument PDF změněno tak, aby odpovídalo velikosti metasouboru. Když je tato funkce povolena, velikost písma WMF se přizpůsobí velikosti metasouboru, což může zmenšit velikost generovaného dokumentu PDF.

#### Otázka: Jak mohu pomocí Aspose.Words for .NET povolit nebo zakázat změnu velikosti písem WMF na velikost metasouboru v dokumentu PDF?
Odpověď: Chcete-li povolit nebo zakázat změnu velikosti písem WMF na velikost metasouboru v dokumentu PDF pomocí Aspose.Words for .NET, postupujte takto:

 Nahrazením nastavte cestu k adresáři, kde jsou umístěny vaše dokumenty`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

 Vložte dokument, který chcete zpracovat, pomocí`Document` třídy a zadejte cestu k dokumentu aplikace Word v zadaném adresáři dokumentů.

 Nakonfigurujte možnosti vykreslování metasouboru vytvořením instance souboru`MetafileRenderingOptions` třídy a nastavení`ScaleWmfFontsToMetafileSize`majetek do`true` povolit změnu velikosti písem WMF na velikost metasouboru nebo na`false` pro zakázání této funkce.

 Nakonfigurujte možnosti uložení jako PDF vytvořením instance souboru`PdfSaveOptions` třídy a pomocí dříve nakonfigurovaných možností vykreslování metasouborů.

 Uložte dokument ve formátu PDF pomocí`Save` metoda`Document` třída určující cestu a možnosti uložení.

#### Otázka: Jaké jsou výhody změny velikosti písem WMF na velikost metasouboru v dokumentu PDF?
Odpověď: Výhody změny velikosti písem WMF na velikost metasouboru v dokumentu PDF jsou:

Zmenšení velikosti souboru PDF: Změna velikosti písem WMF na velikost metasouboru může snížit velikost generovaného dokumentu PDF přizpůsobením velikosti písma potřebám metasouboru.

Vylepšený výkon: Přizpůsobením velikosti písem WMF rozměrům metasouboru může být vykreslování dokumentu PDF rychlejší a efektivnější.