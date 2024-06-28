---
title: Aktualizovat naposledy vytištěnou vlastnost v dokumentu PDF
linktitle: Aktualizovat naposledy vytištěnou vlastnost v dokumentu PDF
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce aktualizací vlastnosti "Last Printed" při převodu do PDF pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Tento článek obsahuje podrobného průvodce, jak používat vlastnost "Poslední tisk" ve funkci aktualizace dokumentu PDF pomocí Aspose.Words for .NET. Každou část kódu si podrobně vysvětlíme. Na konci tohoto tutoriálu budete schopni porozumět tomu, jak nakonfigurovat možnost aktualizace vlastnosti "Poslední tisk" při převodu do PDF.

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

## Krok 3: Nakonfigurujte možnosti Uložit jako PDF s aktualizovanou vlastností „Poslední vytištění“.

 Chcete-li povolit aktualizaci vlastnosti "Poslední vytištěno" při převodu do PDF, musíme nakonfigurovat`PdfSaveOptions` objekt a nastavte`UpdateLastPrintedProperty`majetek do`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Krok 4: Uložte dokument jako PDF s aktualizací vlastnosti "Poslední tisk".

Nakonec můžeme dokument uložit ve formátu PDF pomocí dříve nakonfigurovaných možností uložení.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

To je vše ! Úspěšně jste povolili aktualizaci vlastnosti "Last Printed" při převodu dokumentu do PDF pomocí Aspose.Words for .NET.

### Příklad zdrojového kódu pro aktualizaci vlastnosti "Last Printed" pomocí Aspose.Words pro .NET


```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Závěr

V tomto tutoriálu jsme vysvětlili, jak aktualizovat vlastnost "Last Printed" v dokumentu PDF pomocí Aspose.Words for .NET. Podle uvedených kroků můžete snadno nakonfigurovat možnost aktualizace vlastnosti "Poslední vytištění" při převodu dokumentu do PDF. Pomocí této funkce můžete sledovat využití dokumentů a související informace.

### Často kladené otázky

#### Otázka: Co je vlastnost "Last Printed" v dokumentu PDF?
Odpověď: Vlastnost "Naposledy vytištěno" v dokumentu PDF odkazuje na datum a čas, kdy byl dokument naposledy vytištěn. Tato vlastnost může být užitečná pro sledování informací o používání a správě dokumentů.

#### Otázka: Jak mohu aktualizovat vlastnost "Last Printed" v dokumentu PDF pomocí Aspose.Words for .NET?
A: Chcete-li aktualizovat vlastnost "Last Printed" v dokumentu PDF pomocí Aspose.Words for .NET, postupujte takto:

 Vytvořte instanci souboru`Document` třídy určující cestu k dokumentu aplikace Word.

 Vytvořte instanci souboru`PdfSaveOptions` třídu a nastavte`UpdateLastPrintedProperty`majetek do`true` povolit aktualizaci vlastnosti "Naposledy vytištěno".

 Použijte`Save` metoda`Document`třídy pro uložení dokumentu ve formátu PDF zadáním možností uložení.

#### Otázka: Jak mohu zkontrolovat, zda byla ve vygenerovaném dokumentu PDF aktualizována vlastnost "Last Printed"?
Odpověď: Můžete zkontrolovat, zda byla vlastnost "Poslední vytištěno" ve vygenerovaném dokumentu PDF aktualizována otevřením souboru PDF v kompatibilním prohlížeči PDF, jako je Adobe Acrobat Reader, a zobrazením informací o dokumentu. Datum a čas posledního tisku by měl odpovídat datu a času generování PDF dokumentu.
