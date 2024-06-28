---
title: Nastavte možnosti obrysu v dokumentu PDF
linktitle: Nastavte možnosti obrysu v dokumentu PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce nastavením možností obrysu v dokumentu PDF pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/set-outline-options/
---

Tento článek obsahuje podrobného průvodce, jak používat nastavení možností osnovy pro funkci velikosti metasouboru s Aspose.Words pro .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto kurzu budete schopni porozumět tomu, jak nastavit možnosti osnovy v dokumentu a vygenerovat PDF s odpovídajícími možnostmi osnovy.

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

## Krok 3: Nakonfigurujte možnosti uložení jako PDF s možnostmi plánu

Chcete-li nastavit možnosti obrysu ve vygenerovaném PDF, musíme nakonfigurovat`PdfSaveOptions` objekt. Můžeme nastavit počet úrovní osnovy nadpisů (`HeadingsOutlineLevels`) a počet úrovní rozšířené osnovy (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Krok 4: Uložte dokument jako PDF s možnostmi obrysu

Nakonec můžeme dokument uložit ve formátu PDF pomocí dříve nakonfigurovaných možností uložení.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

To je vše ! Úspěšně jste nastavili možnosti osnovy v dokumentu a vygenerovali PDF s odpovídajícími možnostmi osnovy pomocí Aspose.Words pro .NET.

### Příklad zdrojového kódu pro nastavení možností plánu na velikost metasouboru pomocí Aspose.Words pro .NET


```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Závěr

V tomto tutoriálu jsme vysvětlili, jak nastavit možnosti obrysu v dokumentu PDF pomocí Aspose.Words for .NET. Pomocí popsaných kroků můžete snadno určit úrovně nadpisu a obrysu v dokumentu a vygenerovat soubor PDF s odpovídajícími možnostmi obrysu. Využijte výhod možnosti osnovy ke zlepšení struktury a navigace v dokumentech PDF pomocí Aspose.Words for .NET.

### Často kladené otázky

#### Otázka: Jaká je možnost osnovy v dokumentu PDF?
Odpověď: Volba osnovy v dokumentu PDF odkazuje na hierarchickou strukturu obsahu dokumentu. Umožňuje vytvořit interaktivní obsah a usnadňuje navigaci v dokumentu. Možnosti obrysu určují úrovně titulků a titulků, které se mají zahrnout do obrysu, a úroveň podrobností, které se mají zobrazit ve vygenerovaném obrysu.

#### Otázka: Jak mohu nastavit možnosti obrysu v dokumentu PDF pomocí Aspose.Words for .NET?
Odpověď: Chcete-li nastavit možnosti osnovy v dokumentu PDF pomocí Aspose.Words pro .NET, postupujte takto:

 Nahrazením nastavte cestu k adresáři, kde jsou umístěny vaše dokumenty`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři vašich dokumentů.

 Načtěte dokument, který chcete převést do PDF, pomocí`Document` třídy a zadejte cestu k dokumentu v zadaném adresáři dokumentů.

 Nakonfigurujte možnosti uložení jako PDF vytvořením instance souboru`PdfSaveOptions` třídy a pomocí`OutlineOptions` vlastnost pro nastavení možností osnovy. Počet úrovní nadpisů, které se mají zahrnout do osnovy, můžete určit pomocí`HeadingsOutlineLevels` vlastnost a počet úrovní rozšířeného obrysu pomocí`ExpandedOutlineLevels` vlastnictví.

 Uložte dokument ve formátu PDF pomocí`Save` metoda`Document` třída určující cestu a možnosti uložení.

#### Otázka: Jaká je možnost plánu v dokumentu PDF?
Odpověď: Volba osnovy v dokumentu PDF vám umožňuje vytvořit hierarchickou strukturu obsahu, která usnadňuje navigaci v dokumentu a přístup k různým sekcím. To umožňuje uživatelům rychle přejít na konkrétní části dokumentu kliknutím na položky v obsahu nebo osnově. Možnost osnovy také zlepšuje zážitek ze čtení tím, že poskytuje přehled o celkové struktuře dokumentu.
