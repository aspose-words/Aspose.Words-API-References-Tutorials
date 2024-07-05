---
title: Komprese obrázků v dokumentu PDF
linktitle: Komprese obrázků v dokumentu PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Krok za krokem průvodce kompresí obrázků v dokumentu PDF s Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/image-compression/
---

Tento článek poskytuje krok za krokem průvodce, jak používat funkci komprese obrázků v dokumentu PDF s Aspose.Words pro .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto tutoriálu budete schopni porozumět tomu, jak komprimovat obrázky v dokumentu a generovat PDF se správnou kompresí obrázků.

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

## Krok 3: Nakonfigurujte možnosti uložení jako PDF s kompresí obrazu

 Chcete-li komprimovat obrázky při převodu do PDF, musíme nakonfigurovat`PdfSaveOptions` objekt. V případě potřeby můžeme nastavit typ komprese obrazu, kvalitu JPEG a další možnosti souladu s PDF.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Krok 4: Uložte dokument jako PDF s kompresí obrazu

Nakonec můžeme dokument uložit ve formátu PDF pomocí dříve nakonfigurovaných možností uložení.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Krok 5: Nakonfigurujte možnosti pro ukládání do PDF/A-2u s kompresí obrazu

Pokud chcete generovat PDF kompatibilní s PDF/A-2u s kompresí obrazu, můžete nakonfigurovat další možnosti ukládání.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Použijte kompresi JPEG s 50% kvalitou pro zmenšení velikosti souboru.
};
```

## Krok 6: Uložte dokument jako PDF/A-2u s kompresí obrazu

Uložte dokument ve formátu PDF/A-2u pomocí dalších možností uložení nakonfigurovaných dříve.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



To je vše ! Úspěšně jste zkomprimovali obrázky v dokumentu a vygenerovali PDF se správnou kompresí obrázků pomocí Aspose.Words for .NET.

### Ukázka zdrojového kódu pro kompresi obrázků pomocí Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Použijte kompresi JPEG v 50% kvalitě pro zmenšení velikosti souboru.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Závěr

V tomto tutoriálu jsme vysvětlili, jak komprimovat obrázky v dokumentu PDF pomocí Aspose.Words for .NET. Podle popsaných kroků můžete snadno zmenšit velikost obrázků v dokumentu PDF a vygenerovat PDF se správnou kompresí obrázků. Použijte funkce komprese obrázků Aspose.Words for .NET k optimalizaci velikosti vašich dokumentů PDF při zachování kvality obrazu.

### Často kladené otázky

#### Otázka: Co je komprese obrazu v dokumentu PDF?
Odpověď: Komprese obrazů v dokumentu PDF má za cíl zmenšit velikost obrazů obsažených v dokumentu PDF, aby se zmenšila celková velikost souboru PDF. To snižuje potřebný úložný prostor a zlepšuje výkon při načítání a prohlížení PDF.

#### Otázka: Jak mohu komprimovat obrázky v dokumentu PDF pomocí Aspose.Words for .NET?
Odpověď: Chcete-li komprimovat obrázky v dokumentu PDF pomocí Aspose.Words for .NET, postupujte takto:

 Vytvořte instanci souboru`Document` třídy určující cestu k dokumentu aplikace Word.

 Vytvořte instanci souboru`PdfSaveOptions` třídu a nastavte`ImageCompression`majetek do`PdfImageCompression.Jpeg` použít kompresi JPEG.

Můžete také nastavit další možnosti komprese obrázků, jako je kvalita JPEG, podle vašich potřeb.

 Použijte`Save` metoda`Document`třídy pro uložení dokumentu ve formátu PDF zadáním možností uložení.

#### Otázka: Jaký je rozdíl mezi standardní kompresí obrázků a kompresí obrázků PDF/A-2u?
Odpověď: Standardní komprese obrázků snižuje velikost obrázků v dokumentu PDF při zachování polí formuláře. Tím se zmenší celková velikost souboru PDF, aniž by byla ohrožena funkčnost pole formuláře.

Komprese obrázků pomocí PDF/A-2u je další možnost, která vám umožňuje generovat soubor PDF, který odpovídá standardu PDF/A-2u při použití komprese obrázků. PDF/A-2u je ISO standard pro archivní PDF dokumenty a zaručuje dlouhodobé uchování dokumentů.
